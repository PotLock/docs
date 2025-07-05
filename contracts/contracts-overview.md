---
description: >-
  POTLOCK is a series of smart contracts and decentralized front ends to making
  funding coordination streamlined (potlock.org/core to see all contract source
  code)
---

# 📃 Contracts Overview

## All Contracts

To ensure that all projects are coming from the official POTLOCK team they are deployed as [**subaccounts**](https://docs.near.org/tutorials/crosswords/basics/add-functions-call#create-a-subaccount) under the POTLOCK.near namespace. Testnet and Mainnet follow the same naming conventions to avoid any confusion. There are 7 main contracts, (technically [Pot](pot-live.md) has many contracts as many Pots are deployed under the PotFactory)



## Contract Addresses

### [Donate](donation-live.md) (for a direct donation to any account with referrer fees, optional donations and fungible token support)

Source Code: [https://github.com/PotLock/core/tree/main/contracts/donation](https://github.com/PotLock/core/tree/main/contracts/donation)

Mainnet: [donate.potlock.near](https://nearblocks.io/address/donate.potlock.near)

Testnet: [donate.potlock.testnet](https://testnet.nearblocks.io/address/donate.potlock.testnet)

### **Lists** Contract

Source code: [https://github.com/PotLock/core/tree/main/contracts/lists](https://github.com/PotLock/core/tree/main/contracts/lists)

Mainnet: [lists.potlock.near](https://nearblocks.io/address/lists.potlock.near)

Staging: [lists.staging.potlock.near](https://nearblocks.io/address/lists.staging.potlock.near)

Testnet: [lists.potlock.testnet](https://testnet.nearblocks.io/address/lists.potlock.testnet)

### [**Registry**](registry-deprecated.md) **\[depricated]\(for accounts to add themselves and for owner + admins controlled by the owner to change the status of projects on the registry. Used to display projects and also enforced on Pots for application requirements)**

Source code: [https://github.com/PotLock/core/tree/main/contracts/registry](https://github.com/PotLock/core/tree/main/contracts/registry)

Mainnet:  [registry.potlock.near](https://nearblocks.io/address/registry.potlock.near)

Testnet: [registry.potlock.testnet](https://testnet.nearblocks.io/address/registry.potlock.testnet)

### [**Sybil**](sybil-contract-nadabot.md) **aka nadabot (for people to submit sybil verification stamps from different contracts, users to verify stamps to increase the score to meet the human threshold, and owner + owner controlled admins, to approve & flag stamps, set weights, and set human thresholds, used as a sybil contract aggregator and managed contract enforced human checker)**

Source Code [https://github.com/PotLock/core/tree/main/contracts/sybil](https://github.com/PotLock/core/tree/main/contracts/sybil)

Mainnet: [v1.nadabot.near](https://nearblocks.io/address/v1.nadabot.near)

Staging: [v1.staging.nadabot.near](https://nearblocks.io/address/v1.staging.nadabot.near)

Testnet: [v1.nadabot.testnet](https://testnet.nearblocks.io/address/v1.nadabot.testnet)

### [**Pot Factory**](potfactory-live.md) **(deploys quadratic funding rounds (pots), and sets fees)**

Source code: [https://github.com/PotLock/core/tree/main/contracts/pot\_factory](https://github.com/PotLock/core/tree/main/contracts/pot_factory)

Staging:&#x20;

Testnet: [potfactory.potlock.testnet](https://testnet.nearblocks.io/address/potfactory.potlock.testnet)

### [**Pot**](pot-live.md) **(quadratic funding round deployed by factory contract as a subaccount by anyone that specifies application dates, matching requirements, fees, a chef that can be changed by the owner, where QF payouts are calculated off-chain, initiated on the chain with a cooldown veto period, application & donation requirement according to registry and Sybil contract interfaces and allows anyone to sponsor for matching rounds, and donations to be passed through for optional fees  and to keep track of matching payouts)**

Source Code   [**https://github.com/PotLock/core/tree/main/contracts/pot**](https://github.com/PotLock/core/tree/main/contracts/pot)

Mainnet (whatever you deploy form pot contracts above)

### **Campaigns**

Source Code: [https://github.com/PotLock/core/tree/feat/revised-campaign/contracts](https://github.com/PotLock/core/tree/feat/revised-campaign/contracts)

Testnet: [campaignstest2.potlock.testnet](https://testnet.nearblocks.io/address/campaignstest2.potlock.testnet)

Testnet: [v1.campaigns.potlock.testnet](https://testnet.nearblocks.io/address/v1.campaigns.potlock.testnet)

Mainnet: [v1.campaigns.potlock.near](https://nearblocks.io/address/v1.campaigns.potlock.near)

Staging: [v1.campaigns.staging.potlock.near](https://nearblocks.io/address/v1.campaigns.staging.potlock.near)



### Voting

Source Code: [https://github.com/PotLock/core/tree/voting-contract-mvp](https://github.com/PotLock/core/tree/voting-contract-mvp)

Testnet:&#x20;

Mainnet: [mpdao.vote.potlock.near](https://nearblocks.io/address/mpdao.vote.potlock.near)

Staging: [mpdao.vote.staging.potlock.near](https://nearblocks.io/address/mpdao.vote.staging.potlock.near)



### **Grantpicks**

Source Code: [https://github.com/PotLock/grantpicks/](https://github.com/PotLock/grantpicks/)

Testnet: [v2.grantpicks.potlock.near](https://nearblocks.io/address/v2.grantpicks.potlock.near)



{% content-ref url="potfactory-live.md" %}
[potfactory-live.md](potfactory-live.md)
{% endcontent-ref %}

{% content-ref url="pot-live.md" %}
[pot-live.md](pot-live.md)
{% endcontent-ref %}

{% content-ref url="donation-live.md" %}
[donation-live.md](donation-live.md)
{% endcontent-ref %}

{% content-ref url="attestations-wip/" %}
[attestations-wip](attestations-wip/)
{% endcontent-ref %}

{% content-ref url="sybil-contract-nadabot.md" %}
[sybil-contract-nadabot.md](sybil-contract-nadabot.md)
{% endcontent-ref %}

{% content-ref url="lists-live.md" %}
[lists-live.md](lists-live.md)
{% endcontent-ref %}

{% content-ref url="registry-deprecated.md" %}
[registry-deprecated.md](registry-deprecated.md)
{% endcontent-ref %}

{% hint style="info" %}
Do you have any suggestions for our contracts? Make an[ issue request](https://github.com/PotLock/core/issues/new) on Github today
{% endhint %}

### Mainnet ([potlock.near](https://nearblocks.io/address/potlock.near))



### Testnet ([potlock.testnet](https://testnet.nearblocks.io/address/potlock.testnet))



### Campaigns
Mainnet Staging [v1.campaigns.staging.potlock.near](https://nearblocks.io/address/v1.campaigns.staging.potlock.near) 🔗


Campaigns Contract [https://github.com/PotLock/core/tree/feat/revised-campaign/contracts/campaigns](https://github.com/PotLock/core/tree/feat/revised-campaign/contracts/campaigns) 💻