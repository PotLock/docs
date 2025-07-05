# 🗃️Create Project As DAO

If you're managing an on-chain organization as a DAO (particularly a [Sputnik-DAO](https://github.com/near-daos/sputnik-dao-contract) on NEAR through a [BOS interface](https://near.social/sking.near/widget/DAO.Page?daoId=build.sputnik-dao.near\&tab=proposals)), you can set up your project to have donations and rewards go directly to your DAO treasury.

{% embed url="https://youtu.be/ynVURygnXE0?si=pemUug0S6QmBQsWx" %}

In order to make a proposal to register as a DAO, it is the normal [create project](https://potlock.io/register) flow, however..... you click check the box.

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.44.02 AM.png" alt=""><figcaption><p>Click the register as a DAO checkbox and put a DAO address you have function call proposal access to, then fill out the rest of your profile</p></figcaption></figure>

Note this will also propose to sign up your DAO into NEAR Horizon's project registry, and update your DAO profile. _**While currently this is in 3 separate proposals, we are working to get i into multicall proposal.** You can only propose a DAO to register to POTLOCK if the account you are submitting the proposal from all has the ability to propose function calls (you can suggest your DAO interacts with other contracts)._



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.45.32 AM.png" alt=""><figcaption><p>Example of multiple proposals for updating profile and adding to POTLOCK registry as seperate proposals</p></figcaption></figure>

Then confirm your transaction via your wallet.  Note that for eveyr proposal you will be (bonding or temporarily staking your DAO's bond amount x number of proposal) + spending associated gas costs in NEAR from your DAO treausry.&#x20;

If you already have a DAO proposal to at that DAO address register to POTLOCK, you will see this screen (example of [proposal](https://near.org/sking.near/widget/DAO.Page?daoId=onboarddao.sputnik-dao.near\&tab=proposal\&proposalId=292)).

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.37.15 AM (1).png" alt=""><figcaption><p>DAO Proposal in progress</p></figcaption></figure>

Go to your BOS based DAO proposal (note on [AstroDAO.com](https://app.astrodao.com) or [Astra++](https://near.org/astraplusplus.ndctools.near/widget/home), indexer delays may result in you not seeing your DAO propsoal right away. This is why we use [sking.near DAO's component](https://near.social/sking.near/widget/DAO.Page?daoId=blunt.sputnik-dao.near\&tab=proposals) (replace blunt.sputnik-dao.near with your DAO name) on BOS that pulls straight from NEAR API JS)

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.49.09 AM.png" alt=""><figcaption><p>Approve the 3 proposals relevant to DAO sign up (NEAR Horizon, registry.potlock.near, and socila.near)</p></figcaption></figure>

{% hint style="info" %}
Your proposal will not get passed until all the voting members approve all proposals
{% endhint %}

Although a proposal went through, this only means you are proposing. This means a quorum of your DAO's voting body (those who are allowed to vote on [function call proposals](https://github.com/near-daos/sputnik-dao-contract#roles-and-permissions)) must vote for the DAO's address to execute.

### Example of approved proposals



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.54.10 AM.png" alt=""><figcaption><p>Approved proposal. in this example their is only a council of 1. </p></figcaption></figure>

Now your DAO should be on the POTLOCK project registry[ home page](https://potlock.io/app).&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 12.59.56 AM.png" alt=""><figcaption><p>DAO based profile</p></figcaption></figure>

### Edit Profile As a DAO

If you go to your DAO's profile in an account that has functional call proposal permissions for this DAO, then you will see an edit profile button.

{% embed url="https://youtu.be/ynVURygnXE0?si=zoNXm4QtZI-RuWrD&t=813" %}

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.01.04 AM.png" alt=""><figcaption><p>DAO based profile with edit profile button</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.04.09 AM.png" alt=""><figcaption><p>Make a change in edit project to submit and edit proposal for your near.social page. Note on an edit proposal only social.near contract will be edited so this time will be 1 proposal</p></figcaption></figure>

Next you will confirm you transaction then go to your DAO page and get your voting body to approve the proposal.



<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.06.07 AM.png" alt=""><figcaption><p>Update proposal</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2023-12-10 at 1.07.35 AM.png" alt=""><figcaption><p>Updating project proposal as social.near function call proposal</p></figcaption></figure>

After your voting body approved the DAO proposal, your DAO profile will be updated on NEAR Horizon, POTLOCK registry, and BOS which all pull your profile information to the social.near account.&#x20;
