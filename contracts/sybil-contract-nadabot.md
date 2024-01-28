---
description: Sybil resistance framework - contract based
---

# 🤖 Sybil Contract - NADABOT

{% hint style="info" %}
The Sybil attack in computer security is _an attack wherein a reputation system is subverted by creating multiple identities_
{% endhint %}

Although for direct donations that do not have tax benefits, there is minimal impact if someone is using unique accounts for donations. However, when it comes to democratic voting / funding systems like quadratic funding, we need to make sure that the system is not being gamed and that our subsequent funding contracts are checking for definitions of humans.

[https://app.nada.bot ](https://app.nada.bot)

To solve this Nada.bot has emerged allowing for other sybil providers and contracts to develop "checks" or "stamps" if you are familiar with [Gitcoin Passport's](https://passport.gitcoin.co/) model.&#x20;

{% embed url="https://github.com/PotLock/core/tree/main/contracts/sybil" %}

{% hint style="info" %}
Up to date docs are on[ https://docs.nada.bot ](https://docs.nada.bot)
{% endhint %}



<figure><img src="../.gitbook/assets/nadabotsocialpreview.png" alt=""><figcaption></figcaption></figure>



## Where is this used?

This is\_human check on nadabot.near is used by default in Pot deployments. While a deployer can specify their own configuration for different checks with their own weights and human threshold.



{% hint style="info" %}
See PotDeployer to see how to configure your human check
{% endhint %}

###
