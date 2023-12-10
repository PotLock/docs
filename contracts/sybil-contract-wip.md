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

Although for direct donatiosn that do not have tax benefits, we do not care if someone is using unique accounts, when it comes to democratic voting / funding sysmtems like quadratic funding, we need to make sure that the system is not being gamed and that our subsequent funding contracts are checking for definitions of humans.



We have invented a way for other sybil providers and contracts to develop "checks" or "stamps" if you are familiar with [Gitcoin Passport's](https://passport.gitcoin.co/) model.&#x20;



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

This is\_human check on sybil.potlock.near is used by defailt in Pot deployments. While a deployer can specify their own configuration for different checks with their own weights and human threshold.

## Can I customize

## How We Determine Humans

Although



## Future of Contract

We invision&#x20;
