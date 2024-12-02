---
description: >-
  A single contract for raising for a specific initiative with optional time or
  target based restraints
---

# 💲 Campaigns \[live]

Campaigns on PotLock provide a structured way to raise funds for specific initiatives associated with an account, with optional minimum escrowed targets.

#### Overview of Campaigns

Campaigns serve as a vehicle for raising funds toward defined goals or initiatives. They introduce minimum funding targets and operate within a specified timeframe, allowing for refunds if the target is not met. This feature encourages community engagement and provides clarity on funding purposes, making it ideal for both individual projects and broader organizational objectives.

### Use Cases

* **Targeted Fundraising**: Raise funds specifically for initiatives like events, projects, or community support.
* **Supporting Organizations**: Individuals can create campaigns on behalf of organizations to expand outreach and impact.
* **Community Engagement**: Enable fans and supporters to contribute towards their favorite projects, fostering a sense of ownership and participation.

### Features of Campaigns

* **Single Currency Support**: Each campaign can support only one currency at a time, simplifying transactions.
* **Beneficiary Approval**: The beneficiary (the project or organization being funded) can officially approve the campaign, ensuring transparency.
* **Escrow Functionality**: Donations may be held in escrow until the minimum target is reached; if not met, donors are refunded.
* **Referral Opportunities**: Campaign creators can leverage optional referral systems to encourage more community participation in fundraising efforts.



### Contract Structure

The PotLock Campaign Contract is designed to facilitate fundraising through donations while managing escrow functionalities based on specified targets.

**General Types**

```rust
type CampaignId = u64;
type DonationId = u64;
type TimestampMs = u64;
type ReferrerPayouts = HashMap<AccountId, Balance>;
```

* **CampaignId**: Unique identifier for each campaign.
* **DonationId**: Unique identifier for each donation instance.
* **TimestampMs**: Represents time in milliseconds.

**Contract Fields**

The main contract structure includes several key fields:

* **owner**: The account that created the campaign.
* **admins**: Accounts with administrative privileges over the campaign.
* **next\_campaign\_id**: Tracks the ID assigned to the next campaign created.
* **campaigns\_by\_id**: Maps campaign IDs to their details.
* **donations\_by\_id**: Maps donation IDs to their details.
* **escrowed\_donation\_ids\_by\_campaign\_id**: Maps campaign IDs to donations held in escrow.

```rust
pub struct Contract {
    contract_source_metadata: LazyOption<VersionedContractSourceMetadata>,
    owner: AccountId,
    admins: IterableSet<AccountId>,
    protocol_fee_basis_points: u32,
    protocol_fee_recipient_account: AccountId,
    default_referral_fee_basis_points: u32,
    default_creator_fee_basis_points: u32,
    next_campaign_id: CampaignId,
    campaigns_by_id: IterableMap<CampaignId, VersionedCampaign>,
    campaign_ids_by_owner: IterableMap<AccountId, IterableSet<CampaignId>>,
    campaign_ids_by_recipient: IterableMap<AccountId, IterableSet<CampaignId>>,
    next_donation_id: DonationId,
    donations_by_id: IterableMap<DonationId, VersionedDonation>,
    escrowed_donation_ids_by_campaign_id: IterableMap<CampaignId, IterableSet<DonationId>>,
    unescrowed_donation_ids_by_campaign_id: IterableMap<CampaignId, IterableSet<DonationId>>,
    returned_donation_ids_by_campaign_id: IterableMap<CampaignId, IterableSet<DonationId>>,
    donation_ids_by_donor_id: IterableMap<AccountId, IterableSet<DonationId>>,
    storage_deposits: IterableMap<AccountId, Balance>,
}

/// NOT stored in contract storage; only used for get_config response
pub struct Config {
    pub owner: AccountId,
    pub admins: Vec<AccountId>,
    pub protocol_fee_basis_points: u32,
    pub protocol_fee_recipient_account: AccountId,
    pub default_referral_fee_basis_points: u32,
    pub default_creator_fee_basis_points: u32,
    pub total_campaigns_count: u64,
    pub total_donations_count: u64,
}
```



**Campaign Structure**

Each campaign includes:

* **name**: Title of the campaign.
* **description**: Overview of what the campaign aims to achieve.
* **cover\_image\_url**: URL for the campaign's cover image.
* **recipient**: Account receiving the funds raised by the campaign.
* **start\_ms / end\_ms**: Timestamps indicating when the campaign starts and ends.
* **target\_amount / min\_amount / max\_amount**: Financial targets associated with the campaign.

NB: Campaigns can be created on behalf of others, hence the recipient field.

```rust
pub struct Campaign {
    pub owner: AccountId,
    pub name: String,
    pub description: Option<String>,
    pub cover_image_url: Option<String>,
    pub recipient: AccountId,
    pub start_ms: TimestampMs,
    pub end_ms: Option<TimestampMs>,
    pub created_ms: TimestampMs,
    pub ft_id: Option<AccountId>,
    pub target_amount: Balance,
    pub min_amount: Option<Balance>,
    pub max_amount: Option<Balance>,
    pub total_raised_amount: Balance,
    pub net_raised_amount: Balance,
    pub escrow_balance: Balance,
    pub referral_fee_basis_points: u32,
    pub creator_fee_basis_points: u32,
    pub allow_fee_avoidance: bool,
}
```

#### Write Methods

The contract includes several methods for managing campaigns:

* **create\_campaign()**: Initializes a new campaign with specified details.
* **update\_campaign()**: Allows owners to modify existing campaign details.
* **delete\_campaign()**: Removes a campaign from existence.

**NB: ALL privileged write methods (those beginning with `admin_*` or `owner_*`) require an attached deposit of at least one yoctoNEAR, for security purposes.**

{% code overflow="wrap" %}
```rust
// INIT

pub fn new(
        owner: AccountId,
        protocol_fee_basis_points: u32,
        protocol_fee_recipient_account: AccountId,
        default_referral_fee_basis_points: u32,
        default_creator_fee_basis_points: u32,
        source_metadata: ContractSourceMetadata,
    ) -> Self {


// Campaign

#[payable]
pub fn create_campaign(
        &mut self,
        name: String,
        description: Option<String>,
        cover_image_url: Option<String>,
        recipient: AccountId,
        start_ms: TimestampMs,
        end_ms: Option<TimestampMs>,
        ft_id: Option<AccountId>,
        target_amount: U128,
        min_amount: Option<U128>,
        max_amount: Option<U128>,
        referral_fee_basis_points: Option<u32>,
        creator_fee_basis_points: Option<u32>,
        allow_fee_avoidance: Option<bool>,
    ) -> CampaignExternal
    

#[payable]
pub fn update_campaign(
   &mut self,
   campaign_id: CampaignId,
   name: Option<String>,
   description: Option<String>,
   cover_image_url: Option<String>,
   start_ms: Option<TimestampMs>,
   end_ms: Option<TimestampMs>,
   ft_id: Option<AccountId>,
   target_amount: Option<Balance>,
   max_amount: Option<Balance>,
   min_amount: Option<U128>, // Can only be provided if campaign has not started yet
   allow_fee_avoidance: Option<bool>,
   // NB: recipient cannot be updated. If incorrect recipient is specified, campaign should be deleted and recreated
) -> CampaignExternal {


pub fn delete_campaign(&mut self, campaign_id: CampaignId)

// Donation 
#[payable]
pub fn donate(
        &mut self,
        campaign_id: CampaignId,
        message: Option<String>,
        referrer_id: Option<AccountId>,
        bypass_protocol_fee: Option<bool>,
        bypass_creator_fee: Option<bool>,
    ) -> PromiseOrValue<DonationExternal> {


// STORAGE

pub fn storage_deposit(&mut self) -> U128

pub fn storage_withdraw(&mut self, amount: Option<U128>) -> U128


// OWNER

#[payable]
pub fn owner_change_owner(&mut self, owner: AccountId)

pub fn owner_add_admins(&mut self, admins: Vec<AccountId>)
pub fn owner_remove_admins(&mut self, admins: Vec<AccountId>)
pub fn owner_clear_admins(&mut self)

// SOURCE METADATA

pub fn self_set_source_metadata(&mut self, source_metadata: ContractSourceMetadata) // only callable by the contract account (reasoning is that this should be able to be updated by the same account that can deploy code to the account)
```
{% endcode %}

#### Donation Methods

Users can donate through:

* **donate()**: Allows users to contribute funds to an active campaign, specifying optional messages or referrer IDs.

#### Read Methods

The contract provides various read methods:

* **get\_campaign()**: Retrieves details of a specific campaign by ID.
* **get\_campaigns\_by\_owner()**: Lists all campaigns created by a specific account.
* **get\_donations\_for\_campaign()**: Provides all donations made towards a specific campaign.

{% code overflow="wrap" %}
```rust
// CONFIG

pub fn get_config(&self) -> Config

// CAMPAIGNS
get_campaign(&self, campaign_id: CampaignId) -> CampaignExternal

get_campaigns(
        &self,
        from_index: Option<u128>,
        limit: Option<u128>,
    ) -> Vec<CampaignExternal>
    

pub fn get_campaigns_by_owner(
        &self,
        owner_id: AccountId,
        from_index: Option<u128>,
        limit: Option<u128>,
    ) -> Vec<CampaignExternal>

pub fn get_campaigns_by_recipient(
        &self,
        recipient_id: AccountId,
        from_index: Option<u128>,
        limit: Option<u128>,
    ) -> Vec<CampaignExternal>



// DONATIONS
pub fn get_donations(&self, from_index: Option<u128>, limit: Option<u64>) -> Vec<DonationExternal>

pub fn get_donation_by_id(&self, donation_id: DonationId) -> Option<DonationExternal>

pub fn get_donations_for_campaign(
        &self,
        campaign_id: CampaignId,
        from_index: Option<u128>,
        limit: Option<u64>,
    ) -> Vec<DonationExternal>

pub fn get_donations_for_donor(
        &self,
        donor_id: AccountId,
        from_index: Option<u128>,
        limit: Option<u64>,
    ) -> Vec<DonationExternal>


// STORAGE

pub fn storage_balance_of(&self, account_id: &AccountId) -> U128


// OWNER

pub fn get_owner(&self) -> AccountId


// SOURCE METADATA

pub fn get_contract_source_metadata(&self) -> Option<ContractSourceMetadata>
```
{% endcode %}

#### Events

Events are emitted during significant actions within the contract:

* A `campaign_create` event indicates that a new Campaign object has been created.

This structured overview provides a comprehensive understanding of how campaigns function within PotLock, detailing their purpose, features, contract structure, and methods effectively.

**Example:**

{% code overflow="wrap" %}
```rust
{
  "standard": "potlock",
  "version": "1.0.0",
  "event": "campaign_create",
  "data": [
    {
      "campaign": {
        "owner": ""
      }
    }
  ]
}
```
{% endcode %}

#### `set_source_metadata`



Indicates that `ContractSourceMetadata` object has been set/updated.

**Example:**

```rust
{
  "standard": "potlock",
  "version": "1.0.0",
  "event": "set_source_metadata",
  "data": [
    {
      "source_metadata": {
        "commit_hash": "ec02294253b22c2d4c50a75331df23ada9eb04db",
        "link": "https://github.com/PotLock/core",
        "version": "0.1.0"
      }
    }
  ]
}
```

{% embed url="https://github.com/PotLock/core/tree/feat/campaigns/contracts/campaigns" %}





## Contract Adresses

When the contracts will be deployed they will be audited as they can custody funds. After the audit the contracts will be locked at

v1.campaigns.potlock.testnet

v1.campaigns.potlock.near

v1..campaigns.staging.potlock.near



