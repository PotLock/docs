---
description: Frequently asked questions
---

# ❓ FAQ

## General FAQ

What is considered a public good?

* A public good is generally considered a project that provides more value creation than extraction. For projects that approved on our registry; check out [https://potlock.org/guidelines](https://potlock.org/guidelines)

What if I don't qualify as a public good?

* You can check out our uncensored version showing all pots and unapproved projects in registry soon. Will be hosted at uncensored.potlock.org

Why do you have referrals?

* To gamify and incentivize a decentralized referral network. A donor can always take out the referredId from URL and this will make it so referrer does not get fee. Also on pots fees can be zero and this can be used to keep track of who brings in more people.

Are fees mandatory?

* Fees on the pot level are determined by pot owner. However from the factory contract that is locked (check https;//potlock.org/changelog) has max fees for protocol, chefs, and referrer to prevent abuse by pot owner. Additionally a pot deployer can see fees for all parties to zero (or less than max). For direct donations fees are also optional. Front ends may not reflect this at the moment.

What blockchain and currencies do you currently support?

* We are on the NEAR Blockchain, a highly performant layer 1 blockchain,. Our quadratic funding contracts support the nativer crypto currency NEAR, while our direct donation contract supports any fungible token. (We are still adjusting front end). Star our core contract repos for any relevant update [https://github.com/potlock/core](https://github.com/potlock/core)

What is quadratic funding?

* Quadratic funding is a novel funding mechanisms that incentivies smaller unqiue contributions against a matching pool. Learn more at [https://wtfisqf.com](https://wtfisqf.com/)

Do you have a token?

* We currently do not have a token. But we are interested in providing incentiv ies for those who provide regular impact. If you do tokenomics or want to contribute to a discussion like this, check out the Potlock community telegram?

What is next after quadratic funding?

* We are working on public goods legos on how to compose these interfaces. Currently we are designing campaigns for anyone to launch. More information can be found in our roadmap (also checkout our designs at [https://potlock.org/figma](https://potlock.org/figma)

How is nada.bot related to Potlock?

* It is a sybil contract aggregator we are spinning to address our immediate sybil needs in the ecosystem. We aggregate with outher sybil providers. Check out [https://nada.bot/support](https://nada.bot/support) if you have any questions and [https://docs.nada.bot](https://docs.nada.bot/) to integrate

Is Potlock a platform or a protocol?

* Potlock is a protocol, a collection of platforms, and an ecosystem for public goods funding, and impact tracking. however, anyone can fork or use our technology at standard for reoutfitting funding mechanisms for any set of accounts and changing donor requirements. Check out our [ecosystem ideas board](https://potlock.org/ideas) on how to get started

## Project FAQ

Why isn't my project showing up on explore section of main Potlock gateway?

* need to be approved by an admin.

How much do projects usually get funding?

* You can see average donation amount for approved projects on our registry at statistics at potlock.org/flipside and we will be having more data dashboards soon. Currently funding rounds in total would not exceed $40,000 about as February 2024 when we are launching, so consider that a cap. However we are using participation in round and growth in impact and justification for higher rounds in the future. We encourage other funding mechanisms and plural funding mechanisms, and creating a profile with attestations will increase the odds of getting other funding sources. Join the Potlock ecosystem chat if you need support with higher direct grants from a funding vertical on NEAR, a multichain ecosystem grant, or if you are looking to transition to a private company with appropriate accelerators. We are here as a public good to support projects making an impact in the space, and even if you don't consider yourself a public good, we are here to help!

How to do I get on the featured projects page?

* Contact [Potlock Community](https://potlock.org/community). Currently we are just randomly picking projects we like and that are undervalues. In the future with creation of a more robust curation system we can better democratize this or automate this based on trending donations>

## Developer FAQ

Is there a place to test on testnet?

* No currently we are justing on staging you can test on our BOS app. As we build a traditional app you can check testnet there. Our testnet contracts can be found at [https://docs.potlock.io/contracts/contracts-overview](https://docs.potlock.io/contracts/contracts-overview)

Who is involved in ecosystem?

* Their are alot of different contributors to potlock ecosystem, check them out at [https://ecosystem.potlock.org/#active-contributors](https://ecosystem.potlock.org/#active-contributors)

What license is Potlock front ends and contracts under?

* We are under a MIT open source license, and encourage others to fork us and build new funding mechanisms

How do I get involved building?

* Check out our [backlog](https://potlock.org/backlog) for "good-first-issues" and join our [Potlock Community](https://potlock.org/community)chat ot introduce yourself

What are ways you mtigate risks?

* Opsec. Locking our contracts and after audits so their is no backdoor. Redundant front ends and decentralized gateways with different einvronments. Open source building so anyone can fork us if they dont like us.

Do you have any middleware or any indexers?

* No currently but we are looking to speed up performance. We are currently relying on NEAR's public RPC. We pull all data form onchain collection of contracts, check out our bos-app and gateway.

What tech stack are you building on?

* We build on BOS, which is a React like JSX framework, our smart contracts are in Rust, and use NextJS for our traditional app we are building. We also use Schell for some scripts, and Markdown for documentation. Data analysts use SQL and Python for data queries. If you are looking to contribute and build in the Potlock ecosystem, we can support a wide array of stacks.

Do you have a security audit?

* We have two from Ottersec and [Guvenkaya](https://potlock.org/guvenkaya) for our contracts and can be found in https;//github.com/potlock/core "audits" repo, but as we develop more contracts for the funding stack, we will get more audit programs. We currently do not have an active bug bounty program, but contact us at [support@potlock.org](mailto:support@potlock.org) or reach out to admin on community telegram for responsible disclosure so we can address in a timely fashion
