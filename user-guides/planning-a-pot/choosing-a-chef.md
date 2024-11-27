# 🔎 Choosing a Chef

Just as the name implies, the chef is akin to a skilled cook in a bustling kitchen, responsible for crafting a delicious meal that satisfies everyone at the table. A great chef selects the finest ingredients, prepares each dish with care, and ensures that everything comes together perfectly. Similarly, in a funding round, the chef manages applications, verifies projects, and coordinates with donors and sponsors.

Selecting a chef is important. This person should not only have domain expertise in the pot's vertical or focus area to approve applications, but they should also possess knowledge of the Potlock platform (see us for training), have a network to raise funds, provide custom support experience, and be a trustworthy individual.

### Managing Chefs and Sometimes Performing Chef Roles

As a pot owner or admin, you are responsible for ensuring that the chef adheres to guidelines and that there is no wrongdoing. You always have the option to select a new chef. Since there can only be one chef at a time and you hold all the permissions of the chef, you may also be involved in promoting the round, helping donors get verified, assisting projects with applications, approving projects, and so forth.

### Advertised Funds for Matching Are Put on Contract from Sponsor's Account Ahead of Time

When deploying a round, ensure that if you are marketing it for a certain amount, the sponsor has deposited the matching amount directly into the contract after deployment. All payments and fees occur directly on-chain.

### Ensuring No Wrongdoing in Chef Payouts and Checking During the Cooldown Period

The actual calculations involve taking donation information from the pot against the matching amount to determine what the quadratic funding will be.



### For Owners

This section is relevant only for pot owners (and admins who can change the settings of a pot). When you deploy a pot, you are creating your own contract. This process will cost 4.4 NEAR. There are essential aspects you can customize about your rounds:

* **Information:** The only things you cannot change are the title of the pot and its description.
* **Dates:** Specify the application start and end dates as well as the matching round start and end dates. Your matching round cannot start before applications open. You can keep applications open during the matching round and push back dates if necessary. Applications indicate when projects can apply, while the matching round denotes when people can start donating.
* **Fees:** This includes protocol fees, referrer fees, and chef fees. The factory contract—responsible for deploying this contract—has maximum protocol, referrer, and chef fees that can be set to zero. A protocol fee takes a percentage of every matched donation and sponsorship received. The chef fee incentivizes more donations and sponsorships to grow the pot. Referrer fees are generated through links shared when a donation or sponsorship is made, providing a kickback to incentivize public participation in growing the pot. The public can view these settings.
* **Eligibility:** Project and donor requirements must be specified. Choose the registry (list) that projects must be on to be eligible; this is usually the Potlock public goods registry (projects listed on bos.potlock.org). Additionally, donor requirements need to be established; by default, nada.bot verifies that donors are human through an application that allows users to verify different services to build up their human score. Optional minimum donation amounts can also be set.
* **Admins and Chefs:** Admins are individuals who can change settings as well as reallocate chefs; they are optional roles. Chefs are responsible for accepting applications. Both admins and you as the owner can perform any actions that a chef can do. Chefs will receive fees for growing the pot.

