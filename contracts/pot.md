---
description: A pot is a funding round
---

# 🍲 Pot



{% hint style="info" %}
{name}.pot.potlock.near or {name}.pot.potlock.testnet
{% endhint %}

## How Pots Can Differ

The major differences in a pot are defined in the PotFactory contract&#x20;

* Which SBT as user must hold to donate (most time will be I-Am-Human SBT)
* Application time period and round time period
* Whether there are milestones and number of milestoned, and percentage of funds raised paid up front
  * If there are milestones, what is threshold amount of fund raise to require milestones be turned in
* Number of max projects

## Managing As A Round Manager

As a round manager you can&#x20;

* accept or reject new applications during application period. You cannot accept applications if there is a max number of projects and their are already that many applicants.&#x20;
* approve or disprove a milestone (with a reason). Part of the most difficult part of being a Round Manager or a Chef is that you are literally reviewing grants on a rolling basis. Whether a project completed a milestone, by comparing what they outline in the milestone in their Pot application, compared to the milestoneEvidence they submitted.&#x20;



Questions

* What happens if a milestone is disproved? Can it be resubmitted?



## Applying As A Project

* Contract requires you be on the Potlock Registry ([registry.potlock.near](registry.md))
* You can submit an application with any relevant information&#x20;
  * If their are milestones, you must put in specific milestone information for the number of milestones required for this pot

## Donating as a Donor

* You must be a verified human unless other SBTs are specified by factory contract
* You choose the project and funding round.
* Their is a function to donate (it is important to note thatpart of your donation a small fee is given to protocol and the Chef
