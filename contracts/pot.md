---
description: A pot is a funding round
---

# 🍲 Pot



{% hint style="info" %}
{name}.pot.potlock.near or {name}.pot.potlock.testnet
{% endhint %}

## How Pots Can Differ

The major differences in a pot are defined in the PotFactory contract&#x20;

* Donor Requirements: Which SBT as user must hold to donate (most time will be I-Am-Human SBT)
* Application time period (when a project can apply and the Pot's Chef approve & rejects application) and round time period (when external contributions come in)
* **Number of Milestones:** Whether there are milestones and number of milestones. All number of milestones are the same for every project, unless they did no meat the treshold amount.
  * If there are milestones, what is threshold amount of fund raise to require milestones be turned in
  * &#x20; percentage of funds raised paid up front. How much if there are milestones is pad up front. The rest is equally divided by milestone
  * There is a max number of 3 milestones set by the PotFactory to prevent over administrative work and too small payouts for projects.
* **Number of max projects:** whether there are a number of max projects to prevent over saturation of rounds. Up to the Pot's Chef to filter this.
* **Currency**: For now on MVP we are only allowing for NEAR rounds to reduce complexity. In the future we will be supporting fungible tokens, mostly rolling out USDC and USDT based rounds.

## Phases of A Pot

* **Pre-Kitchen**: this is before a Pot is deployed. This maybe preparing soft commits from donors, and planning and communication off-chain with potential Chef and DAO council
* **Application-Period**: When applications are open and the Pot's Chef is filtering though application. At this time Patrons can also donate to the amount that is matched.
* **Applicants-Finalized**: This is the period before matched donations start. Patrons can also donated to the matched amount. No more projects can apply anymore.&#x20;
* **Matched-Donations:** When verified humans can get their contributions matched. Up until this point all matched donations were not a thing. Patrons can also donated to matched amounts. Only at the end of the Pot (when donations close) are the amount each proejcts earn is calculated. Up until this point all matching is estimated by a calculator component, based on current contributions and current matching pool. No one can calculate this amount until all matched donations and the their are no more additional funds to funding round. At the end of this all payouts or upfront payouts for milestone rounds are initiated (or r[eady for claims -- still up for debate](https://github.com/orgs/PotLock/discussions/5))
* **Milestone-Submission (Optional)**: This is an ongoing period, if there are milestones, where projects submit milestone evidence, the Pot's Chef compares to applications, and rejects or accepts the milestone. If milestone is rejected a project can re-submit evidence.  Payouts for milestones happen to this period
* **Closed**: All payouts have happened for every project. If this a milestone round than this means every milestone has been paid out.&#x20;

<figure><img src="../.gitbook/assets/potphases.png" alt=""><figcaption></figcaption></figure>

## Managing As A Round Manager

As a round manager you can&#x20;

* accept or reject new applications during application period. You cannot accept applications if there is a max number of projects and their are already that many applicants.&#x20;
* approve or disprove a milestone (with a reason). Part of the most difficult part of being a Round Manager or a Chef is that you are literally reviewing grants on a rolling basis. Whether a project completed a milestone, by comparing what they outline in the milestone in their Pot application, compared to the milestoneEvidence they submitted.&#x20;



## Applying As A Project

* Contract requires you be on the Potlock Registry ([registry.potlock.near](registry.md))
* You can submit an application with any relevant information&#x20;
  * If their are milestones, you must put in specific milestone information for the number of milestones required for this pot

## Donating as a Donor

* You must be a verified human unless other SBTs are specified by factory contract
* You choose the project and the amount.
* Their is a function to donate (it is important to note that part of your donation a small fee is given to protocol and the Chef



## Changing Criterion

* Pot managers (particular chef) can change SBT criterion, say in the event, it becomes higher level of funding round based on donations, or I-Am-Human is not enough to prevent sybil resistance.&#x20;
*

    <figure><img src="../.gitbook/assets/Screenshot 2023-08-28 at 12.53.25 PM.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2023-08-28 at 12.54.22 PM.png" alt=""><figcaption></figcaption></figure>

## Questions

* Claiming vs Automatic Payouts [https://github.com/orgs/PotLock/discussions/5](https://github.com/orgs/PotLock/discussions/5)&#x20;
