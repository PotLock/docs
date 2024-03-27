---
description: Lists allow anyone to create a
---

# 📜 Lists \[live]

Think of lists like Spotify playlists for any account.

Lists are currently enforced in latest version of quadratic funding contracts (aka pots), that enable a criterion for accounts to be able to apply.&#x20;

## Use Cases

* Create your own curated playlists of projects that let people donate quicker
* Build membership requirements
* Populate token ownerships and airdrop waitlists based on these lists
* Create your own explore page of Potlock for individuals, corporations, and non-public goods
* Get community signal through upvotes
* Create donate to all flow for lists to easily support a wide basket of project
* Create signal for projects like RetroPGF



## Features

#### Roles

* Owner, Admin, Registrant, User

Owner

* An owner is the person who made the list
* They can add or remove admins
* transfer ownership
* Update status for an account on list
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

The primary goal of the PotLock Lists Contract is to provide a flexible platform where anyone can create and manage their own lists of accounts (referred to as "registrants"). This functionality is particularly useful for organizing groups, communities, or any collection of Near Protocol accounts based on specific criteria or for specific purposes. The contract supports self-registration by accounts as well as registration management by list owners and admins.

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

* We have made it easy to render relationships with lists
* can easily query lists by an admin, to see your lists
* can query accounts to see all the lists they are on
* see upvotes for a lists
* see all uvpotes for an account (aka my "liked" lists)
* can see when the registration was and whether their is any notes from registration or admin (admin can add note on approval)
* Query functions for lists and registrations, including getting lists by owner or registrant, registration details by ID, and checking if an account is registered with a specific status on a list.

{% hint style="info" %}
The contract includes various  [events](https://github.com/PotLock/core/tree/main/contracts/lists#events) to log significant actions like list creation, updates, deletion, registration management, and source metadata updates.
{% endhint %}



Contract: [https://github.com/PotLock/core/tree/main/contracts/lists](https://github.com/PotLock/core/tree/main/contracts/lists)

Example JS implementation ([BOS](https://docs.near.org/bos)) [https://github.com/PotLock/bos-app/blob/main/apps/potlock/widget/SDK/lists.jsx ](https://github.com/PotLock/bos-app/blob/main/apps/potlock/widget/SDK/lists.jsx)
