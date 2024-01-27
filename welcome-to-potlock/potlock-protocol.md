---
description: Describes PotLock as an open source public good anyone can fork
---

# 🔓 PotLock Protocol

Potlock is a protocol for deploying any funding strategy, impact tracking and engagement tools for public goods. We are completely open source, modular, and permissionless from day 1.. If you don't like us we encourage forks.&#x20;



## Deep Dive Into the "Legos"

[https://potlock.org/legos](https://potlock.org/legos) and [https://potlock.org/legos-explained](https://potlock.org/legos-explained)

As we build we are developing the concept of legos.&#x20;



<figure><img src="../.gitbook/assets/Screenshot 2024-01-27 at 5.22.27 AM.png" alt=""><figcaption><p>low fidelity of creating funding strategies</p></figcaption></figure>

## Potlock Ecosystem

Potlock is composed of projects, protocol, communities, contributors that make this happen. See the entire ecosystem at [https://ecosystem.potlock.org ](https://ecosystem.potlock.org)

Tech That We Use\



| Tech Stack                               | About                                                                                                                                                                                                                                                                                                             | How We Are Using                                                                     | Why                                                                                                                                                                                                                          |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [BOS](http://docs.near.org/bos)          | a front end framework for development where JSX code is stored as composable components on the social.near contract the NEAR blockchain that can be rendered across different clients ([gateways](http://near.org/gateways))                                                                                      | We are using for our entire front ends on our app.                                   | Allows use to easily fork existing components.                                                                                                                                                                               |
| [NEAR](https://near.org/)                | A layer 1 blockchain with smart contracts on Rust.                                                                                                                                                                                                                                                                | We are building smart contracts, using existing contracts like social.near,          | Cheap and fast transactions. Their is no quadratic funding contract.                                                                                                                                                         |
| [NEAR Horizon](https://near.org/horizon) | An accelerator platform on NEAR where founders, contributors and service providers can interact & interface both leveraging the nearhorizon.near contract and social.near contract built as a BOS native platform. Partners with accelerator in the ecosystem, is open source, and serves as a project directory. | As a project directory and pipelining organization to existing accelerator partners. | Projects must registers, allow us to easily onboard to accelerator, and public good projects already on NEAR Horizon to sign up for Potlock. Already existing components we can fork with support from the NEAR Foundation.  |
| [Keypom](https://keypom.xyz/)            | An onboarding protocol leveraging NEAR’s account model that allows for the creation of linkdrops that allow someone with or without a wallet to claim & automate a series of actions. Also enabling trial accounts for users.                                                                                     | Using to onboard users to platform.                                                  | Can use for donors to claim, and trail accounts without needing for people to use password.                                                                                                                                  |
