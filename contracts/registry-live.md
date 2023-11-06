# 🗺 Registry \[live]

{% hint style="info" %}
registry.potlock.near & registry.potlock.tetnet
{% endhint %}

## Overview

The PotLock project registry allow us to query projects that have signed up to our project onboarding which uses contracts like [nearhorizon.near](https://nearblocks.io/address/nearhorizon.near) and [social.near](https://nearblocks.io/address/social.near), but also lets round managers to curate projects to prevent from getting spammed.



Code&#x20;

{% embed url="https://github.com/PotLock/core/tree/main/contracts/registry" %}



Deployed Contract

{% embed url="https://nearblocks.io/address/registry.potlock.near" %}

Setters

* Projects can be only only by project addressed or whitelisted owner
  * Reccomended use a named account with projects name on it or subject to be added to graylist
  * All projects that signup through traditional flow will be putting on whitelist (approved), admins must trigger a status change to be taken off
* an owner (DAO) can add admins that can add project manually to the registry or can change the status of the project (put on blacklist or graylist or approve a project)

Getters

* can check wether a project is on registry
* can check the status of a projects
* can get the last projects on the whitelist, graylist, and blacklist

What is the difference between graylist and blacklist

* graylist is if we are unsure this is a legit project
* blacklist is surely not a legit project, it also may be a personal account, spam, or cointain inappropriate content

<figure><img src="../.gitbook/assets/Screenshot 2023-08-25 at 6.20.30 PM.png" alt=""><figcaption></figcaption></figure>



