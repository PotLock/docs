---
description: >-
  Our sybil resistance framework is known as Nada.bot and its contract is a
  sybil.potlock.near
---

# ✏ Sybil Contract \[wip]

{% embed url="https://nearblocks.io/address/sybil.potlock.near" %}

{% hint style="info" %}
The Sybil attack in computer security is _an attack wherein a reputation system is subverted by creating multiple identities_
{% endhint %}

Although for direct donations that do not have tax benefits, there is minimal impact if someone is using unique accounts for donations. However, when it comes to democratic voting / funding systems like quadratic funding, we need to make sure that the system is not being gamed and that our subsequent funding contracts are checking for definitions of humans.



We have invented a way for other sybil providers and contracts to develop "checks" or "stamps" if you are familiar with [Gitcoin Passport's](https://passport.gitcoin.co/) model.&#x20;

{% embed url="https://github.com/PotLock/core/tree/main/contracts/sybil" %}

## Terms

**Checks**: a NEAR contract + method name that takes in an accountId and returns a boolean, that is used as a 3rd party identity service. Think contract APis.&#x20;

**Human Threshold:** points through aggregated checks x wieghts an individual must have after calculate\_score(accountId) function is called&#x20;

**Sybil Provider:** someone/an organization who submits a check and matains verification + a contract for a check.

## Formatting Your Check

The format are checks are contract methods  (getter functions) in which you pass in an accountID and returns a boolean value.&#x20;



We prefer you deploy your contract under a named account, preferably as a subaccount like twitter.womrhol3.near so users can trust your entity for maintaining this contract.

For example; say you create a contract that binds as twitter account to, you will create a helper function that can be called to view whether an account has successfully binded on both ends. You do not have to create a mapping contract method. For example we are not asking you return the twitter account ID, rather we just are trusting that you just verify if an account has compelted a certain check. For example on twitter.wormhol3.near you would have a method isTwitterVerified(accountId): bool.  Currently it is up to the PotLock Sybil team to determine weights based on impact of check and trustworthiness of entity.&#x20;





## Reference Implementations of Checks

#### I-Am-Human registry

I am human is a registry contract that issues SBT based on Fractal's face verification to issue a SBT according to NEP 393. This was using in the first NDC election to verify humans for a vote. We leverage the registry is\_human method to check if someone has a face scan without the need for PotLock's contributor to keep track or having a Fractal api. &#x20;



#### Womrhol3 Binding

Wormhole is a contract that binds using twitter API and singing a transaction to delegate wormhole3.near social signer contract to post twitter posts with the hashtag #BOS to social.near post section of data tree. Since twitter API can cost around $5,000 a month for this, we are using the \_\_\_\_ method on their contract, to check if their twitter is verified.&#x20;



[https://github.com/wormhole3/wormhole3-account-binding/tree/main/contract](https://github.com/wormhole3/wormhole3-account-binding/tree/main/contract)

## How to Submit Your Check

In order to submit your check go to nada.bot and click submit your check. In  the submit check, you are to&#x20;

* Put your contract name, method. We will then check if it returns a boolean and takes in an accountId in the correct format.&#x20;
* Add information about your check, what APIs you use, etc.&#x20;
* Add a  link to near personal or organization account for the entity mantaining this
* Add a URL for how to verify with this check.&#x20;





## Where is this used?

This is\_human check on sybil.potlock.near is used by default in Pot deployments. While a deployer can specify their own configuration for different checks with their own weights and human threshold.



{% hint style="info" %}
See PotDeployer to see how to configure your human check
{% endhint %}

### Why Use Our Human Check&#x20;

We will be running funding pools that bad actors will try to game. Not only will be verifying independent checks by different sybil providers, we will be adjusting weights based on importance, and human thresholds as addresses try to bot us in realtime. Additionally if our requirements are too strong we can adjust these to make more accesible. Most application developers and round maangers / chefs will not be monitoring all addresses that interact with their contract, rather relying on our aggregated "check"&#x20;



#### U**s Vs idOS**

While their are other identity layer providers, Nada.bot is for NEAR contracts that need to use a cross contract call that is robust instead of idOS which is an SDK to be integrated into applications.&#x20;

## How We Determine Humans

On our contract we set weights and approves. Currently we are toggling based on different weights (see on [nada.bot](https://nada.bot))



## Future of Contract

We invision this as a DAO / sybil research WG that different data & monitoring groups use to better exmplofy what is a human. Additionally we will be working with different teams to proilfierate creating contracts to verify third parties. Eventually we look to spin out the Nada.bot core team outside the PotLock core team and are making steps to do so.&#x20;
