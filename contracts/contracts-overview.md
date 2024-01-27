---
description: >-
  PotLock is a series of smart contracts and decentralized front ends to making
  funding coordination streamlined (potlock.org/core to see all contract source
  code)
---

# 📃 Contracts Overview

## All Contracts

To assure that all projects are coming from the official PotLock team they are deployed as [**subaccounts**](https://docs.near.org/tutorials/crosswords/basics/add-functions-call#create-a-subaccount) under the potlock.near namespace. Testnet and Mainnet follow the same naming conventions to avoid any confusion. Their are 7 main contracts, (technically [Pot](pot-wip.md) has many contracts as many Pots are deployed under the PotFactory)



## Contract Addresses

#### Donate (for direct donation to any account with referrer fees, optional donations and fungible token support)

Source Code [https://github.com/PotLock/core/tree/main/contracts/donation](https://github.com/PotLock/core/tree/main/contracts/donation)

Mainnet [donate.potlock.near](https://nearblocks.io/address/donate.potlock.near)

Testnet [donate.potlock.testnet](https://testnet.nearblocks.io/address/donate.potlock.testnet)

**Registry (for accounts to add themselves and for owner + admins controlled by owner to change status of projects on registry. Used to display projects and also enforced on Pots for application requirements)**

Source code [https://github.com/PotLock/core/tree/main/contracts/registry](https://github.com/PotLock/core/tree/main/contracts/registry)

Mainnet  [registry.potlock.near](https://nearblocks.io/address/registry.potlock.near)

Testnet [registry.potlock.testnet](https://testnet.nearblocks.io/address/registry.potlock.testnet)

**Sybil aka nadabot (for people to submit sybil verification stamps from different contracts, users to verify to stamps to increase score to meet human threshold, and owner + owner controlled admins, to approve & flag stamps, set wieghts, and set human thresholds, used as a sybil contract aggregator and managed contract enforced human checker)**

Source Code [https://github.com/PotLock/core/tree/main/contracts/sybil](https://github.com/PotLock/core/tree/main/contracts/sybil)

Mainnet [v1.nadabot.near](https://nearblocks.io/address/v1.nadabot.near)

Staging [v1.staging.nadabot.near](https://nearblocks.io/address/v1.staging.nadabot.near)

Testnet [v1.nadabot.testnet](https://testnet.nearblocks.io/address/v1.nadabot.testnet)

**Pot Factory (deploys quadratic funding rounds (pots), and sets fees)**

Source code [https://github.com/PotLock/core/tree/main/contracts/pot\_factory](https://github.com/PotLock/core/tree/main/contracts/pot\_factory)

Staging: potfactory2.tests.potlock.near

**Pot (quadratic funding round deployed by factory contract as a subaccount by anyone that specifies application dates, matching requirements, fees, a chef that can be changed by owner, where QF payouts are calculated off chain, initiated on chain with a cooldown veto period, application & donation requirement according to registry and sybil contract interfaces and allows anyone to sponsor for matching rounds, and donations to be passed through for optional fees  and to keep track of matching payouts)**

Source Code   [**https://github.com/PotLock/core/tree/main/contracts/pot**](https://github.com/PotLock/core/tree/main/contracts/pot)

Mainnet (whatever you deploy form pot contracts above)

{% content-ref url="potfactory-wip.md" %}
[potfactory-wip.md](potfactory-wip.md)
{% endcontent-ref %}

{% content-ref url="pot-wip.md" %}
[pot-wip.md](pot-wip.md)
{% endcontent-ref %}

{% content-ref url="donation-live.md" %}
[donation-live.md](donation-live.md)
{% endcontent-ref %}

{% content-ref url="registry-live.md" %}
[registry-live.md](registry-live.md)
{% endcontent-ref %}

{% content-ref url="attestations-hyperfiles-wip/" %}
[attestations-hyperfiles-wip](attestations-hyperfiles-wip/)
{% endcontent-ref %}

{% content-ref url="sybil-contract-nadabot-wip/" %}
[sybil-contract-nadabot-wip](sybil-contract-nadabot-wip/)
{% endcontent-ref %}

{% hint style="info" %}
Do you have any suggestions for our contracts? Make an[ issue request](https://github.com/PotLock/core/issues/new) on Github today
{% endhint %}

### Mainnet ([potlock.near](https://nearblocks.io/address/potlock.near))



### Testnet ([potlock.testnet](https://testnet.nearblocks.io/address/potlock.testnet))



{% hint style="warning" %}
Warning: none of our contracts are audited, matter of fact we haven't even wrote the contract yet, super building in public vibes.
{% endhint %}
