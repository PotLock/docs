---
description: Lists allow anyone to create a
---

# 📜 Lists \[live]

Think of lists like Spotify playlists for any account.

Lists are currently enforced in the latest version of quadratic funding contracts (aka pots), that enable a criterion for accounts to be able to apply.&#x20;

## Use Cases

* Create your own curated playlists of projects that let people donate quicker
* Build membership requirements
* Populate token ownerships and airdrop waitlists based on these lists
* Create your own explore page of POTLOCK for individuals, corporations, and non-public goods
* Get community signal through upvotes
* Create donate to all flow for lists to easily support a wide basket of project
* Create a signal for projects like RetroPGF



## Features

#### Roles

* Owner, Admin, Registrant, User

Owner

* An owner is the person who made the list
* They can add or remove admins
* transfer ownership
* Update the status of an account on the list
* Set default status -> all applications are default pending
* Add accounts or remove accounts (in batches)

On List Creation (tutorial soon)

* Choose Name, Description, Cover Photo of List
* Add Admins (optional)
* Allow Application (optional) aka admin\_only\_registration

Admin

* Can do everything an owner does except add or remove other admins

Registrant

* Can register&#x20;
* Can unregister (cannot remove self from list if added by admin)
* _This only applies if applications are open_ aka **no admin\_only\_registration**

User (any account)

* can upvote or un-upvote (no downvotes)
* can apply to list if application open



Our public goods registry lives on list\_id = 1, where we have the official display and other applications index our lists.

## On the [Contract](https://github.com/PotLock/core/tree/main/contracts/lists)

The primary goal of the POTLOCK Lists Contract is to provide a flexible platform where anyone can create and manage their own lists of accounts (referred to as "registrants"). This functionality is particularly useful for organizing groups, communities, or any collection of Near Protocol accounts based on specific criteria or for specific purposes. The contract supports self-registration by accounts as well as registration management by list owners and admins.

### Contract Structure

#### General Types

* `RegistrantId`: Alias for `AccountId`, representing an account on the list.
* `RegistrationId`: A unique identifier for a registration instance, used to track individual registrations.
* `ListId`: A unique identifier for each list created within the contract.
* `TimestampMs`: Represents time in milliseconds.

#### Contract

The main contract structure (`Contract`) contains several key fields:

* `next_list_id`: Tracks the ID to be assigned to the next list created.
* `next_registration_id`: Tracks the ID to be assigned to the next registration.
* Various mappings to manage lists, registrations, list ownership, list administrators, and registrant relationships.

#### Lists

* **Internal Representation**: `ListInternal` includes details such as name, description, cover image URL, owner, creation and update timestamps, and registration status management.
* **External View**: `ListExternal` is used for external queries, including additional details like total registration and upvote counts.

#### Registrations

Defines the status of registrations (`RegistrationStatus`) and structures for managing registration details both internally (`RegistrationInternal`) and externally (`RegistrationExternal`).



**Write Methods**

* **Initialization**: `new` to set up the contract with initial source metadata.
* **List Management**: Methods to create, update, delete lists,  upvotes & remove upvote, and handle ownership and admin rights.
* **Registrations**: Functions to manage batch registrations, unregister accounts, and update registration details (like admins updating status).

{% hint style="info" %}
All writes method require deposit of 1 yocto NEAR
{% endhint %}

[**Read**](https://github.com/PotLock/core/tree/main/contracts/lists#general-types) **Methods**

{% hint style="info" %}
The contract includes various&#x20;
{% endhint %}



Contract: [https://github.com/PotLock/core/tree/main/contracts/lists](https://github.com/PotLock/core/tree/main/contracts/lists)

Example JS implementation ([BOS](https://docs.near.org/bos)) [https://github.com/PotLock/bos-app/blob/main/apps/potlock/widget/SDK/lists.jsx ](https://github.com/PotLock/bos-app/blob/main/apps/potlock/widget/SDK/lists.jsx)



## Interface

````markdown
# POTLOCK Lists Contract

## Purpose

Anyone can curate their own list of accounts ("registrants"). Accounts can register to be on a list, or be added to a list by the owner or admins. An owner can add and remove list admins, or transfer ownership. An owner or admin can update the list name & description.

## Contract Structure

### General Types

```rs
type RegistrantId = AccountId;
type RegistrationId = u64;
type ListId = u64;
type TimestampMs = u64;
```

### Contract

```rs
pub struct Contract {
    /// Incrementing ID to assign to new lists
    next_list_id: ListId,
    /// Incrementing ID to assign to new registrations
    next_registration_id: RegistrationId,
    /// Lists indexed by List ID
    lists_by_id: UnorderedMap<ListId, VersionedList>,
    /// Lookup from owner account ID to List IDs they own
    list_ids_by_owner: UnorderedMap<AccountId, UnorderedSet<ListId>>,
    /// Lookup from registrant ID to List IDs it belongs to
    list_ids_by_registrant: UnorderedMap<RegistrantId, UnorderedSet<ListId>>,
    /// List admins by List ID
    list_admins_by_list_id: LookupMap<ListId, UnorderedSet<AccountId>>,
    /// List registrants by ID
    // NB: list_id is stored on registration
    registrations_by_id: UnorderedMap<RegistrationId, VersionedRegistrationInternal>,
    /// Lookup from List ID to registration IDs
    registration_ids_by_list_id: UnorderedMap<ListId, UnorderedSet<RegistrationId>>,
    /// Lookup from Registrant ID to registration IDs
    registration_ids_by_registrant_id: UnorderedMap<RegistrantId, UnorderedSet<RegistrationId>>,
    /// Lookup from List ID to upvotes (account IDs)
    upvotes_by_list_id: LookupMap<ListId, UnorderedSet<AccountId>>,
    /// Contract "source" metadata
    contract_source_metadata: LazyOption<VersionedContractSourceMetadata>,
}
```

### Lists

```rs
// ListInternal is the data structure that is stored within the contract
pub struct ListInternal {
    // don't need ID since it's the key, but should include in ListExternal
    pub name: String, // max length 64
    pub description: Option<String>, // max length 256
    pub cover_img_url: Option<String>, // must start with https://
    pub owner: AccountId,
    pub created_at: TimestampMs,
    pub updated_at: TimestampMs,
    pub default_registration_status: RegistrationStatus,
    pub admin_only_registrations: bool, // defaults to false
    // consider adding list status, e.g. draft, active, inactive, etc.
}

// Ephemeral data structure used for view methods, not stored within contract
pub struct ListExternal {
    pub id: ListId,
    pub name: String,
    pub description: Option<String>,
    pub cover_img_url: Option<String>,
    pub owner: AccountId,
    pub admins: Vec<AccountId>,
    pub created_at: TimestampMs,
    pub updated_at: TimestampMs,
    pub default_registration_status: RegistrationStatus,
    pub admin_only_registrations: bool,
    pub total_registrations_count: u64,
    pub total_upvotes_count: u64,
}
```

### Registrations

```rs
pub enum RegistrationStatus {
    Pending,
    Approved,
    Rejected,
    Graylisted,
    Blacklisted,
}

// RegistrationInternal is the data structure that is stored within the contract
pub struct RegistrationInternal {
    // don't need to store ID since it's the key
    pub registrant_id: AccountId,
    pub list_id: ListId,
    pub status: RegistrationStatus,
    pub submitted_ms: TimestampMs,
    pub updated_ms: TimestampMs,
    pub admin_notes: Option<String>,
    pub registrant_notes: Option<String>,
    pub registered_by: AccountId, // Could be list owner or a list admin. If None, use registrant_id. Used for processing refund on deletion of registration.
}

// Ephemeral data structure used for view methods, not stored within contract
pub struct RegistrationExternal {
    pub id: RegistrationId,
    pub registrant_id: AccountId,
    pub list_id: ListId,
    pub status: RegistrationStatus,
    pub submitted_ms: TimestampMs,
    pub updated_ms: TimestampMs,
    pub admin_notes: Option<String>,
    pub registrant_notes: Option<String>,
    pub registered_by: AccountId,
}

// Ephemeral struct for admins to use when registering a registrant
#[derive(BorshDeserialize, BorshSerialize, Serialize, Deserialize, PartialEq, Debug, Clone)]
#[serde(crate = "near_sdk::serde")]
pub struct RegistrationInput {
    pub registrant_id: AccountId,
    pub status: RegistrationStatus,
    pub submitted_ms: Option<TimestampMs>,
    pub updated_ms: Option<TimestampMs>,
    pub notes: Option<String>,
}

```

## Methods

### Write Methods

**NB: ALL privileged write methods (those restricted to a list owner or admin) require an attached deposit of at least one yoctoNEAR, for security purposes.**

```rs
// INIT

pub fn new(source_metadata: ContractSourceMetadata) -> Self


// LISTS

#[payable]
pub fn create_list(
    &mut self,
    name: String,
    description: Option<String>,
    cover_image_url: Option<String>,
    admins: Option<Vec<AccountId>>,
    default_registration_status: RegistrationStatus,
    admin_only_registrations: Option<bool>,
) -> ListExternal
// NB: Caller will be the list owner
// emits create_list event

#[payable]
pub fn update_list(
    &mut self,
    list_id: ListId,
    name: Option<String>,
    description: Option<String>,
    cover_image_url: Option<String>,
    remove_cover_image: Option<bool>,
    default_registration_status: Option<RegistrationStatus>,
    admin_only_registrations: Option<bool>,
) -> ListExternal // can only be called by list owner
// emits update_list event

#[payable]
pub fn delete_list(&mut self, list_id: ListId)
// can only be called by list owner
// must attach enough gas to process storage refunds for all registrants; otherwise must delete registrations first
// emits delete_list event

#[payable]
pub fn upvote(&mut self, list_id: ListId)
// if upvote was added, emits upvote event

#[payable]
pub fn remove_upvote(&mut self, list_id: ListId)
// if upvote was removed, emits remove_upvote event

#[payable]
pub fn owner_change_owner(&mut self, list_id: ListId, new_owner_id: AccountId) -> AccountId // returns new owner ID
// emits owner_transfer event

#[payable]
pub fn owner_add_admins(&mut self, list_id: ListId, admins: Vec<AccountId>) -> Vec<AccountId> // returns updated admins
// emits update_admins event

#[payable]
pub fn owner_remove_admins(&mut self, list_id: ListId, admins: Vec<AccountId>) -> Vec<AccountId> // returns updated admins
// emits update_admins event

#[payable]
pub fn owner_clear_admins(&mut self, list_id: ListId) -> Vec<AccountId> // returns updated admins (empty list)
// emits update_admins event


// REGISTRATIONS

#[payable]
pub fn register_batch(
    &mut self,
    list_id: ListId,
    notes: Option<String>, // provided by non-admin registrants
    registrations: Option<Vec<RegistrationInput>>, // provided by admin registrants
) -> Vec<RegistrationExternal>
// emits create_registration event for each Registration created

#[payable]
pub fn unregister(&mut self, list_id: Option<ListId>, registration_id: Option<RegistrationId>) // can only be called by registrant or list owner/admin
// emits delete_registration event

#[payable]
pub fn update_registration(
    &mut self,
    registration_id: RegistrationId,
    status: Option<RegistrationStatus>, // will be ignored unless caller is list owner or admin
    notes: Option<String>, // if called by owner/admin, these will be stored as Registration.admin_notes; otherwise, they will be Registration.registrant_notes
) -> RegistrationExternal
// emits update_registration event


// SOURCE METADATA

pub fn self_set_source_metadata(&mut self, source_metadata: ContractSourceMetadata) // only callable by the contract account (reasoning is that this should be able to be updated by the same account that can deploy code to the account)
// emits set_source_metadata event
```

### Read Methods

```rs
// LISTS

pub fn get_list(&self, list_id: ListId) -> ListExternal

pub fn get_lists(&self, from_index: Option<u64>, limit: Option<u64>) -> Vec<ListExternal>

pub fn get_lists_for_owner(&self, owner_id: AccountId) -> Vec<ListExternal>

pub fn get_lists_for_registrant(&self, registrant_id: AccountId) -> Vec<ListExternal>

pub fn get_upvotes_for_list(
    &self,
    list_id: ListId,
    from_index: Option<u64>,
    limit: Option<u64>,
) -> Vec<AccountId>

pub fn get_upvoted_lists_for_account(
    &self,
    account_id: AccountId,
    from_index: Option<u64>,
    limit: Option<u64>,
) -> Vec<ListExternal>


// REGISTRATIONS

pub fn get_registration(&self, registration_id: RegistrationId) -> RegistrationExternal

pub fn get_registrations_for_list(
    &self,
    list_id: ListId,
    status: Option<RegistrationStatus>,
    from_index: Option<u64>,
    limit: Option<u64>,
) -> Vec<RegistrationExternal>

pub fn get_registrations_for_registrant(
    &self,
    registrant_id: AccountId,
    status: Option<RegistrationStatus>,
    from_index: Option<u64>,
    limit: Option<u64>,
) -> Vec<RegistrationExternal>

pub fn is_registered(
    &self,
    list_id: Option<ListId>, // Optional for now because it has to be compatible with current Pot implementation of RegistryProvider, which calls a contract providing only "account_id" arg
    account_id: RegistrantId,
    required_status: Option<RegistrationStatus>, // defaults to Approved
) -> bool


// SOURCE METADATA

pub fn get_contract_source_metadata(&self) -> Option<ContractSourceMetadata>
```

### Events

```rs
/// source metadata update
pub(crate) fn log_set_source_metadata_event(source_metadata: &ContractSourceMetadata) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "set_source_metadata",
                "data": [
                    {
                        "source_metadata": source_metadata,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// create list event
pub(crate) fn log_create_list_event(list: &ListExternal) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "create_list",
                "data": [
                    {
                        "list": list
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// update list event
pub(crate) fn log_update_list_event(list: &ListInternal) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "update_list",
                "data": [
                    {
                        "list": list,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// delete list event
pub(crate) fn log_delete_list_event(list_id: ListId) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "delete_list",
                "data": [
                    {
                        "list_id": list_id,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// upvote list event
pub(crate) fn log_upvote_event(list_id: ListId, account_id: AccountId) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "upvote",
                "data": [
                    {
                        "list_id": list_id,
                        "account_id": account_id,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// remove upvote list event
pub(crate) fn log_remove_upvote_event(list_id: ListId, account_id: AccountId) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "remove_upvote",
                "data": [
                    {
                        "list_id": list_id,
                        "account_id": account_id,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// update (add or remove) admins event
pub(crate) fn log_update_admins_event(list_id: ListId, admins: Vec<AccountId>) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "update_admins",
                "data": [
                    {
                        "list_id": list_id,
                        "admins": admins,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// owner transfer event
pub(crate) fn log_owner_transfer_event(list_id: ListId, new_owner_id: AccountId) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "owner_transfer",
                "data": [
                    {
                        "list_id": list_id,
                        "new_owner_id": new_owner_id,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// create registration event
pub(crate) fn log_create_registration_event(registration: &RegistrationExternal) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "create_registration",
                "data": [
                    {
                        "registration": registration,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// update registration event
pub(crate) fn log_update_registration_event(registration: &RegistrationExternal) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "update_registration",
                "data": [
                    {
                        "registration": registration,
                    }
                ]
            })
        )
        .as_ref(),
    );
}

/// delete registration event
pub(crate) fn log_delete_registration_event(registration_id: RegistrationId) {
    env::log_str(
        format!(
            "{}{}",
            EVENT_JSON_PREFIX,
            json!({
                "standard": "potlock",
                "version": "1.0.0",
                "event": "delete_registration",
                "data": [
                    {
                        "registration_id": registration_id,
                    }
                ]
            })
        )
        .as_ref(),
    );
}
```

````
