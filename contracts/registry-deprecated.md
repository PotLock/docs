---
description: >-
  The old monolithic official public goods registry has been migrated to the
  first list on the permisionless lists contract which allows anyone to create
  their own registry
---

# 🗺️ Registry \[deprecated]

{% hint style="info" %}
registry.potlock.near & registry.potlock.tetnet
{% endhint %}

## Overview

The POTLOCK project registry allows us to query projects that have signed up to our project onboarding which uses contracts like [nearhorizon.near](https://nearblocks.io/address/nearhorizon.near) and [social.near](https://nearblocks.io/address/social.near), but also lets round managers curate projects to prevent them from getting spammed.



Code&#x20;

{% embed url="https://github.com/PotLock/core/tree/main/contracts/registry" %}



Deployed Contract

{% embed url="https://nearblocks.io/address/registry.potlock.near" %}

Setters

* Projects can be only by project addressed or whitelisted owner
  * Recommended using a named account with the project name on it or subject to be added to the graylist
  * All projects that sign up through traditional flow will be put on the whitelist (approved), and admins must trigger a status change to be taken off
* an owner (DAO) can add admins that can add projects manually to the registry or can change the status of the project (put on blacklist or graylist or approve a project)

Getters

* can check whether a project is on the  registry
* can check the status of a projects
* can get the last projects on the whitelist, graylist, and blacklist

What is the difference between a graylist and a blacklist

* graylist is if we are unsure this is a legit project
* blacklist is surely not a legit project, it also may be a personal account, spam, or contain inappropriate content

<figure><img src="../.gitbook/assets/Screenshot 2023-08-25 at 6.20.30 PM.png" alt=""><figcaption></figcaption></figure>



