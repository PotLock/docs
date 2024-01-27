---
description: Also known as Pots. The following is tutorials for how
---

# Quadratic Funding Tutorials \[WIP]

## How to Apply As A Project

Different pots may have different registry requirements. Most approved pots through Potlock front ends will use Potlock's "APPROVED" registry (registry.potlock.near) as a requirement.  [See Create Your Project ](../create-your-project.md)to see how to do this.  For applications if you have already signed up, its easy as clicking apply (when the application period is live). In order to see that status of your application go to the application tab where a Chef or Owner of the pot will give their reason for accepting or rejecting you.

### As An Approved Project

It is important to note that you can only receive matched donations. If someone gives you a donation from your profile, that is enabled for anyone to do and _**won't be counted towards the matching round**_. It is important that you get donors to verify they are a human through nada.bot eto get donation that can be matched through the matching pool., and this is when the matching period is live. &#x20;



### When I Will Receive Payments

All donations  come directly to the project automatically, and that donation is logged through the Pot (Quadratic funding round) contract to then calculate matching round payouts. The actual payouts from matched amount can only be paid out, when the round is over, when the chef or owner of the Pot initiates the payout calculations, then payouts on chain, and a cooldown period is passed (check timer on pot page). Then all payout amounts can be see on the "Payout" tab.&#x20;

{% hint style="info" %}
Donations must be given through the pot section during when matching period is live by people verified as human through nada bot (or whatever the pot requires) to have their donation amplified.
{% endhint %}

## How to Deploy&#x20;

Currently anyone can deploy quadratic funding round contracts from our  [factory](../../contracts/potfactory-wip.md) contract, but the only deployers of Pots, but through promoted front ends only the deploy button and pots being displayed are to a whitelisted group of deployers so we can assure quality assurance.  To deploy you need to specify

**what can be changed by owner**

* &#x20;application start end end date
* matching round stand and end date
* number of max application
* round description
* who is chef (person who can accept and reject applications, can get a fee of round, and intiaite payouts)

**what cant be change**

* name of contract & round
* need 6 NEAR to deploy as contract



{% hint style="info" %}
Selecting a Chef is important. This person should not only have domain expertise on the Pot's vertiical or focus area to approve applications, but they should have knowledge of the Potlock platform (see us for training), a network to raise funds, custom support experience, and be a trustworth person)
{% endhint %}

## Responsibilities of a Round Owner

Managing Chefs & Sometimes Doing Chef Roles

* As a round owner you are responsible for keeping the chef in line and making sure their isn't any wrong doing. You always have the ability to select a new chef. Also since their can only be one chef and you have all the permissions of the chef, you may also be promoting the round, helping donors get verified, helping projects with application, approve projects with application and so forth.&#x20;

Advertised Funds for Matching Are Put on Contract from Sponsors Account Ahead of Time

* Make sure if you are deploying a round that if you are marketing a round for certain amount, that sponsor put the matching amount directly in the contract after deployment. All payments and fees occur directly on chain.

Making Sure No Wrong Doing for Chef Payouts & Check Down During Cooldown Period

* The actual calculations taking donation information from the pot against matching amount to calculate what the quadratic&#x20;

## Responsibilities of a Chef

A chef is aligned  in incentives as he/she may be getting a small fee of direct donations through rounds and sponsorship through funding round (check pot settings to see what the owner has set the fees to be)&#x20;

* &#x20;As a chef you are responsible for making sure during the application period, that you are approving and rejecting applications in a timely fashion&#x20;
* Raising donations throughout matched donations amount
* Supporting donors with getting verified a sa human through nada bot to donate (this may require telegram support, sending gas fees, etc)
* Working with bot and Sybil protectors to detect wrong doings and potentially rjeect approved applicants&#x20;
* Initiating payouts in a timely fashion
* Organizing a BD sponsor network to grow the Pot



## How to Sponsor

If you want to grow the pot, or put down funds toward the quadratic funding pool for matching, anyone can do this, you do not need to be verified. Just click funding matching amount. Your donation will be taken directly from your account, displayed on our sponsor leaderboard, and logo and link to your NEAR Social profile will be embedded and directly taken from your account. If you are sponsoring from an organization please update your NEAR Social profile with all the relevant information and logo about your organization, as well as if you are an individual. You can sponsor a pot at any point the Pot is deployed to right before when the round ends.&#x20;



## How to Fundraise

Since someone can sponsor at any time, pots can also have referrer fees where by sharing a Pot link (with account Id as referrer id) when a sponsor sponsors from that link, than the referrer get a percentage of that donation. This allows a more decentralized fundraising community. To see the amount in fees check the "Settings" tab of the pot. \[COMING SOON - how to fundraise for a Pot guide].&#x20;

## How to Give As Matched Donation

How do I know if I am elligible to give a matched donation

* It will say it when you are trying to donate through pot

How do I know if I added a donation to a pot instead of just a regular donations

* Their will be a tag on the cart section or on the popup it will say the name of the round.

Where are the best onramping services to get NEAR?

Do Pots taking anything other than NEAR?

* Currrently their is only NEAR support for quadratic funding rounds (pots) while their is fungible token support for direct donations. If you have another token on NEAR please use app.ref.finance to swap.&#x20;

How do I know how much my donation was matched?

* The estiamted amount from UI is not a final amount. Only can see the actual correct amount via calculate payouts when the payouts are intiated in the "Payouts" tab of the Pot page
