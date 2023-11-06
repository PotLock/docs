---
description: >-
  Different funding tiers enables public goods to get funding as they grow and
  make more impact
---

# ♨ Understanding Pots (Funding Rounds)

## What is a Pot?

A pot is a funding round, where patrons can put down on matching rounds, and individual contributors can get rounds matched. ReFI Council deploys a pot and sets a Chef (a round manager) to faciliate applications and milestones.&#x20;



Deep dive into Pot Contract

{% content-ref url="../contracts/pot-wip.md" %}
[pot-wip.md](../contracts/pot-wip.md)
{% endcontent-ref %}

## Phases of A Pot

* **Pre-Kitchen**: this is before a Pot is deployed. This maybe preparing soft commits from donors, and planning and communication off-chain with potential Chef and DAO council
* **Application-Period**: When applications are open and the Pot's Chef is filtering though application. At this time Patrons can also donate to the amount that is matched.
* **Applicants-Finalized**: This is the period before matched donations start. Patrons can also donated to the matched amount. No more projects can apply anymore.&#x20;
* **Matched-Donations:** When verified humans can get their contributions matched. Up until this point all matched donations were not a thing. Patrons can also donated to matched amounts. Only at the end of the Pot (when donations close) are the amount each proejcts earn is calculated. Up until this point all matching is estimated by a calculator component, based on current contributions and current matching pool. No one can calculate this amount until all matched donations and the their are no more additional funds to funding round. At the end of this all payouts or upfront payouts for milestone rounds are initiated (or r[eady for claims -- still up for debate](https://github.com/orgs/PotLock/discussions/5))
* **Milestone-Submission (Optional)**: This is an ongoing period, if there are milestones, where projects submit milestone evidence, the Pot's Chef compares to applications, and rejects or accepts the milestone. If milestone is rejected a project can re-submit evidence.  Payouts for milestones happen to this period
* **Closed**: All payouts have happened for every project. If this a milestone round than this means every milestone has been paid out.&#x20;



<figure><img src="../.gitbook/assets/potphases.png" alt=""><figcaption><p>phases of a pot</p></figcaption></figure>



## Understanding Pot Sizes

In traditional quadratic funding rounds like Gitcoin no matter what level you are at you apply for. Whether you are a startup repository vs Etherscan, generally you are pulling from the same pool of capital. Considering the quadratic funding is inherently a popularity contest, it is disheartening for smaller or less popular projects to be in the same funding rounds or "Pots" as more mature projects. Additionally every new gitcoin round their isn't a direct incentive like their is in Venture Capital for a public good that has shown growth + impact to access higher levels of funding. This why at PotLock we believed in tiered funding rounds, or Pots in which Round Managers aka Chefs allocate SBTs (Soul-Bound Toktnes) based on milestones and our attestation framework for impact to give access to higher levels of capital.



### Pot Sizes

* Dish - $10,000-$50,000&#x20;
* Meal - $50,000-$150,000&#x20;
* Buffet - $150,000-$500,000&#x20;
* Feast - $500,000-$1,000,000

Pots will be consisting of multiple patrons, meaning [Patrons](../user-guides/patrons.md) do not need to donate for the entire Pot Size.&#x20;

