---
description: >-
  PotFactory is the most complex contract we have, it is a factory contract, in
  that it makes quadratic funding
---

# 🏭 PotFactory

[pot.potlock.near ](https://nearblocks.io/address/pot.potlock.near)& pot.potlock.testnet

On the factory contract you can

* Deploy a pot where you can specify the following requirements
  * SBT to donate (Ex; Human SBT) (Indicate by issuer contract and classId)
  * Whether there are milestones and how many. A milestone is a defined deliverable(s) associated  and payouts happen when milestoneEvidence is submitted and a Chef approves this
  * Specify the Chef (aka Round manager), who approves applications and review milestones, and takes a fee. You also specify this fees
  * Time: Start & End Date of Pot, and Stand and End Date of Applications for the Pot&#x20;
  * Max Number of Project in the Round
    * Applications are no longer available once max Number of projects are hit (A Chef approves this amount of projects). This is to prevent over saturation of round and allow for more evenly distributed capital in the found for projects.&#x20;
  * Currency: Set native NEAR or fungible token like USDC as native currency for funding round
* Query All the pots

## How Milestones Are Calculated

* Their is a milestone cap so their is no mangerial oversight hardcoded into factory contract. This
* Milestone threshold, Considering that funding varies based ont traction of individual contributions in a round, their is a milestone threshold, or the amount needed to be raised. The milestone threshold is in the denomination of&#x20;

`if (amountRaisedByProject < milestoneThreshold), then percentPaidOut = 100%`

percentPaidOut indicates. If there are no milestones or amountRaisedByProject < milestone threshold, this means when rounds ends, funding is calculated from matching round, and 100% of the payout happens and the project is not required to submit any milestones. This is to prevent projects from doing operational work when their isn't enough incentvies.&#x20;

if  there is are milestones and a project has raise over the milestone threshold, then the payouts are calculated as the follwoing

```
if (amountRaisedbyProject > milestoneThreshold) {
    payOutPerMilestone = amountRaisedByProject * ((100 - percentPaidOut / numberOfMilestones) / 100) 
}
```

These payouts happen when a milestone is submitted (on the front end this is facilitated through project dashboard by checking whether a project is completely paid out and how many milestones are left), and than the Chef (Round Manager) approves the milestone.&#x20;



## Importance of the Chef

The round manager will be interacting with the Pot contract. This is like a job where they will also be receiving a fee from total round raised for total contributions. This means the success of the round relies on the round manager.&#x20;

* When deploying a pot, you outline who the Chef is an&#x20;
* In theory a chef could be a DAO, however UI will be need to be built to allow a DAO to act on each component



## Questions

* What incentives do Chefs have for wanting to review milestones? When do Chefs get paid?
* When can someone close a round?
* At what points does funding go into the contract? What if round is advertised at certain level and it doesnt hit that threshold?

