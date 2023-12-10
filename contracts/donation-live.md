---
description: >-
  Simple donation contract that allows you to send fungible tokens or NEAR to
  any address with a protocol fee + referral mechanism
---

# 🙏 Donation \[live]

## Contract

Live Deployed Contract&#x20;

{% embed url="https://nearblocks.io/address/donate.potlock.near" %}

Code

{% embed url="https://github.com/PotLock/core/tree/main/contracts/donation" %}

## Why Do A Donation Contract?

Can't you just have people directly submit? Yes, but&#x20;

* we wanted to keep tracking of donations coming through the platform
* we wanted to take a fee for protocol development&#x20;
* we wanted to implement a referral system

## Donation Fees

* For general donations their are 2 fees
* An optional fee if there was  a referral. It is important to note that the referral fee, since it is not gated and anyone can referred to increase donation amount, will not be included in the tax write off amount in Proof of donation.&#x20;
* A protocol fee.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2023-08-25 at 6.50.20 PM.png" alt=""><figcaption></figcaption></figure>



