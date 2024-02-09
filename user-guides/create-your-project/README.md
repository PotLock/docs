---
description: >-
  If you are a public good you can create a project to start receiving donations
  and be eligible for funding rounds.
---

# ➕ Create Your Project

{% embed url="https://youtu.be/_ymKeP-xZcY" %}
Create a project on PotLock
{% endembed %}

To get on our official registry check out the [project guidelines](project-guidelines.md)

## What Happens When You Create A Project

* Get Added to Our Project Registry for donors to explore
* Get added to NEAR Horizon (NEAR Foundation's Founder Success team) Service marketplace (near.org/horizon)
* Create a [NEAR.social](https://near.social) profile (and have you profile discoverable to follow) across all #BOS gateways&#x20;
* In the future: streamline into our global potlock social feed and ease application to future quadratic funding rounds.&#x20;

## How To Create A Project

Any public good can create a project.



{% hint style="warning" %}
_**Note: it is important to that you should only create a project to a named account someone with financial decision power as funds will be going directly to this account & will be used for future rounds . Soon will be able to register as a proejct as a DAO.**_&#x20;
{% endhint %}

To get a named account go to. It will cost approximately 0.05 N - 0.08 N. If you need a linkdrop in order to cover these costs, hop on the NEAR Impact telegram ([https://nearimpact.org/telegram](https://nearimpact.org/telegram)) to receive funds from one of our ecosystem stewards.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-05 at 2.19.56 PM.png" alt=""><figcaption></figcaption></figure>

If you already have data for your organization's profile on NEAR.social, it will automatically pull this information. If not, please put a bio, profile image, banner, tags (for global profile search), select 1 category.&#x20;



Currently you can only choose 1 category. Only choose public good if you do not fall under one category

<figure><img src="../../.gitbook/assets/Screenshot 2023-11-06 at 12.55.33 PM.png" alt=""><figcaption></figcaption></figure>

## Who Should Create A Project

We only support public goods otherwise you will get take off of the [Potlock registry](../../contracts/registry-live.md). Additionally a violation of our [code of conduct](../../general-information/code-of-conduct.md) can also get you taken off the Potlock registry. For a guide on what is considered a public good check out [https://potlock.io/project-guidelines](https://potlock.io/project-guidelines)



## Create A Project As A DAO

Some of you might be managing your on chain organization as a DAO, most notably on near as a [Sputnik-DAO](https://github.com/near-daos/sputnik-dao-contract) through a [BOS interface ](https://near.social/sking.near/widget/DAO.Page?daoId=build.sputnik-dao.near\&tab=proposals)and you donations and rewards to directly go to your DAO treasury.



In order to make a proposal to register as a DAO, it is the normal [create project](https://potlock.io/register) flow, however..... you click check the box.

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.44.02 AM.png" alt=""><figcaption><p>Click the register as a DAO checkbox and put a DAO address you have function call proposal access to, then fill out the rest of your profile</p></figcaption></figure>

Note this will also propose to sign up your DAO into NEAR Horizon's project registry, and update your DAO profile. _**While currently this is in 3 separate proposals, we are working to get i into multicall proposal.** You can only propose a DAO to register to Potlock if the account you are submitting the proposal from all has the ability to propose function calls (you can suggest your DAO interacts with other contracts)._





<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.45.32 AM.png" alt=""><figcaption><p>Example of multiple proposals for updating profile and adding to PotLock registry as seperate proposals</p></figcaption></figure>

Then confirm your transaction via your wallet.  Note that for eveyr proposal you will be (bonding or temporarily staking your DAO's bond amount x number of proposal) + spending associated gas costs in NEAR from your DAO treausry.&#x20;

If you already have a DAO proposal to at that DAO address register to PotLock, you will see this screen (example of [proposal](https://near.org/sking.near/widget/DAO.Page?daoId=onboarddao.sputnik-dao.near\&tab=proposal\&proposalId=292)).

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.37.15 AM (1).png" alt=""><figcaption><p>DAO Proposal in progress</p></figcaption></figure>

Go to your BOS based DAO proposal (note on [AstroDAO.com](https://app.astrodao.com) or [Astra++](https://near.org/astraplusplus.ndctools.near/widget/home), indexer delays may result in you not seeing your DAO propsoal right away. This is why we use [sking.near DAO's component](https://near.social/sking.near/widget/DAO.Page?daoId=blunt.sputnik-dao.near\&tab=proposals) (replace blunt.sputnik-dao.near with your DAO name) on BOS that pulls straight from NEAR API JS)

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.49.09 AM.png" alt=""><figcaption><p>Approve the 3 proposals relevant to DAO sign up (NEAR Horizon, registry.potlock.near, and socila.near)</p></figcaption></figure>

{% hint style="info" %}
Your proposal will not get passed until all the voting members approve all proposals
{% endhint %}

Although a proposal went through, this only means you are proposing. This means a quorum of your DAO's voting body (those who are allowed to vote on [function call proposals](https://github.com/near-daos/sputnik-dao-contract#roles-and-permissions)) must vote for the DAO's address to execute.

Example of approved proposals



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.54.10 AM.png" alt=""><figcaption><p>Approved proposal. in this example their is only a council of 1. </p></figcaption></figure>

Now your DAO should be on the PotLock project registry[ home page](https://potlock.io/app).&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.59.56 AM.png" alt=""><figcaption><p>DAO based profile</p></figcaption></figure>

### Edit Profile As a DAO

If you go to your DAO's profile in an account that has functional call proposal permissions for this DAO, then you will see an edit profile button.

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.01.04 AM.png" alt=""><figcaption><p>DAO based profile with edit profile button</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.04.09 AM.png" alt=""><figcaption><p>Make a change in edit project to submit and edit proposal for your near.social page. Note on an edit proposal only social.near contract will be edited so this time will be 1 proposal</p></figcaption></figure>

Next you will confirm you transaction then go to your DAO page and get your voting body to approve the proposal.



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.06.07 AM.png" alt=""><figcaption><p>Update proposal</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.07.35 AM.png" alt=""><figcaption><p>Updating project proposal as social.near function call proposal</p></figcaption></figure>

After your voting body approved the DAO proposal, your DAO profile will be updated on NEAR Horizon, PotLock registry, and BOS which all pull your profile information to the social.near account.&#x20;
