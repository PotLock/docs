---
description: >-
  PotFactory is the most complex contract we have, it is a factory contract, in
  that it makes quadratic funding
---

# 🏭 PotFactory \[wip]

[pot.potlock.near ](https://nearblocks.io/address/pot.potlock.near)& pot.potlock.testnet

The factory contract can be found here

{% embed url="https://github.com/PotLock/core/tree/main/contracts/pot_deployer" %}

On the factory contract you can

* Deploy a pot where you can specify the following requirements
  * Human check to  donate (See [sybil-contract-nadabot-wip](sybil-contract-nadabot-wip/ "mention")) (Indicate by contract name and methods and respective config)
  * Whether there are milestones and how many. A milestone is a defined deliverable(s) associated  and payouts happen when milestoneEvidence is submitted and a Chef approves this
  * Specify the Chef (aka Round manager), who approves applications and review milestones, and takes a fee. You also specify this fees
  * Time: Start & End Date of Pot, and Stand and End Date of Applications for the Pot&#x20;
  * Max Number of Project in the Round
    * Applications are no longer available once max Number of projects are hit (A Chef approves this amount of projects). This is to prevent over saturation of round and allow for more evenly distributed capital in the found for projects.&#x20;
  * Currency: Set native NEAR or fungible token like USDC as native currency for funding round
* Query All the pots

## Fee Setting & Payments

In the pot factory contract their is Protocol fee and chef fee set

Inside each pot

* **Patron Referral fees**, for funding rounds (Pots): referrals are taken out from funding amount, as well with Protocol fees.&#x20;
  * A patron referral must be a verified human or the contract will ignore this amount and tree as regular patron donation.
  * if there is a 2% referral fee, then $2,000 will be given to referrer address. &#x20;
* **Protocol fees:**&#x20;
  * these are taken out before If the protocol fee is 7%, and a Patron donated $100,000 USD this means $7,000 will be donated to the DAO (impact.sputnik-dao.near) (protocol) account. If registered human.
  * Also taken out of external contributions. If a donor donates $1 USD, then a protocol fee is 7%, and the chef fee is 3%, then ($.90 cents - gas fees) is used as number to calculate what of the matching round goes to projects.
* **Chef fees:** Get paid for external contributions to projects at fixed fee. For example if Chef fee paid out just like protocol fees for external contributions.
  * Chef's do not get a cut for regular donations, since they do not facilitate regular donations
  * Chef's do not get paid when money comes in as its their job to review applications. They get paid their entire fee&#x20;
  * Chef's do not get a cut from bringing in patron donations unless they use their referral link
* For discussions on chef incentives go here [https://github.com/orgs/PotLock/discussions/4](https://github.com/orgs/PotLock/discussions/4)

See [current-fees.md](../welcome-to-potlock/revenue-model/current-fees.md "mention")&#x20;

## How Milestones Are Calculated

* Their is a milestone cap so their is no managerial oversight hardcoded into factory contract. This
* Milestone threshold, Considering that funding varies based on traction of individual contributions in a round, their is a milestone threshold, or the amount needed to be raised. The milestone threshold is in the denomination of&#x20;

`if (amountRaisedByProject < milestoneThreshold), then percentPaidOut = 100%`

percentPaidOut indicates. If there are no milestones or amountRaisedByProject < milestone threshold, this means when rounds ends, funding is calculated from matching round, and 100% of the payout happens and the project is not required to submit any milestones. This is to prevent projects from doing operational work when their isn't enough incentvies.&#x20;

if  there is are milestones and a project has raise over the milestone threshold, then the payouts are calculated as the follwoing

```
if (amountRaisedbyProject > milestoneThreshold) {
    payOutPerMilestone = amountRaisedByProject * ((100 - percentPaidOut / numberOfMilestones) / 100) 
}
```

These payouts happen when a milestone is submitted (on the front end this is facilitated through project dashboard by checking whether a project is completely paid out and how many milestones are left), and than the Chef (Round Manager) approves the milestone.&#x20;

{% hint style="info" %}
In initial MVP when quadratic funding is rolled out milestones will not be included
{% endhint %}



## Who Can Deploy A Pot

Initially the Impact council can deploy a pot. In a pot they determine who the round manager is. This will return error if a specified round manager is not a "chef" role in the impact.sputnik-dao.near contract.



Additionally there is an add\_pot\_deployer() and delete\_pot\_deployer() function for allowing admins to create pots.&#x20;

* This is to prevent managerial oversight for council.
* It is also important to note their is a certain level of marketing and coordination with patrons to make sure a pot is successful

{% hint style="info" %}
In the future will be adding a permissionless pot deployer function
{% endhint %}

## Importance of the Chef

The round manager will be interacting with the Pot contract. This is like a job where they will also be receiving a fee from total round raised for total contributions. This means the success of the round relies on the round manager.&#x20;

* When deploying a pot, you outline who the Chef is an&#x20;
* In theory a chef could be a DAO, however UI will be need to be built to allow a DAO to act on each component
* Since technical payouts are happening under non profit legal wrapper, Chefs fees can be included in contribution write offs, although in external contribution matching it is deducted because quadratic funding calculations are based on what is going to project.&#x20;



## Requirements for Being A Pot Donor

* See [sybil-contract-nadabot-wip](sybil-contract-nadabot-wip/ "mention")

