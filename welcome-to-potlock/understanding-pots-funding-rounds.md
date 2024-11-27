---
description: >-
  Different funding tiers enables public goods to get funding as they grow and
  make more impact
---

# ♨️ Understanding Pots (Funding Rounds)

## What is a Pot?

A pot is a funding round, where patrons can put down on matching rounds, and individual contributors can get rounds matched. Anyone can deploy a pot (for now their is a whitelist) and set  a Chef (a round manager), Pot admins to facilitate the management of the funding round.



Deep dive into [Pot Contract](../contracts/pot-live.md)

{% content-ref url="../contracts/pot-live.md" %}
[pot-live.md](../contracts/pot-live.md)
{% endcontent-ref %}

## Phases of A Pot

* **Pre-Kitchen**: this is before a Pot is deployed. This maybe preparing soft commits from donors, and planning and communication off-chain with potential Chef.
* **Application-Period**: When applications are open and the Pot's Chef is filtering though application. At this time Patrons /Sponsors can also donate to the amount that is matched.
* **Applicants-Finalized**: This is the period before matched donations start. Patrons can also donated to the matched amount. No more projects can apply anymore.&#x20;
* **Matched-Donations / Voting Period:** When verified humans can get their contributions matched. Up until this point donations to projects through the pot contract would not work. Only at the end of the Pot (when donations close) are the amount each projects is getting from the funing pot is calculated. However, on the front end this amount of matching is estimated based on current contributions and current size matching pool. This amount if not final until the challenge period is resolved.
* Payouts + Cooldown: this is when payouts are calculated using offchain quadratic funding calculations based on donations on Pot contract. Then after payouts, the payout method is intiated by chef or owner. Then their is a cooldown period before payout to contest any discrepancies with offchain calculation and onchain payouts amount (check for wrong doing).
* Soon: Compliance Period: This is a new feature that is being implemented. Require that projects have a KYC token in order to receive payouts. Their is a complaince period. If projects in pot don't get the KYC token, then after the compliance period when a Chef/Pot Owner/Pot Admin initaites payouts, the funds "non-compliant" projects would have gotten gets sent to a previosuly specific "remaining funds address".&#x20;
* **Closed**: All payouts have happened. Pot is officially closed



<figure><img src="../.gitbook/assets/potlock-potphases-feb2024-correct.png" alt=""><figcaption></figcaption></figure>

