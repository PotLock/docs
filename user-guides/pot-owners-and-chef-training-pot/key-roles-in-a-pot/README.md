# 🌟 Key Roles in a Pot



{% hint style="info" %}
Alot of people in this kitchen&#x20;
{% endhint %}

### 🔑 Pot Owner

The pot owner is the individual responsible for deploying pots and has full control over their settings. This includes coordinating funding rounds, selecting chefs, managing off-chain sponsors, and removing chefs and other admins as needed.When deploying a pot, the owner creates their own contract, which costs 4.4 NEAR. Here are the essential aspects they can customize:

* **Information:** The only elements that cannot be changed are the title of the pot and its description.
* **Dates:** Specify the application start and end dates, as well as the matching round start and end dates. The matching round cannot start before applications open, but applications can remain open during the matching round, and dates can be pushed back if necessary. Applications indicate when projects can apply, while the matching round denotes when donations can begin.
* **Fees:** This includes protocol fees, referrer fees, and chef fees. The factory contract—responsible for deploying this contract—sets maximum protocol, referrer, and chef fees that can be set to zero. A protocol fee takes a percentage of every matched donation and sponsorship received. The chef fee incentivizes more donations and sponsorships to grow the pot. Referrer fees are generated through links shared during donations or sponsorships, providing a kickback to encourage public participation in growing the pot; these settings are visible to the public.
* **Eligibility:** Project and donor requirements must be specified. Choose the registry (list) that projects must be on to be eligible; this is usually the POTLOCK public goods registry (projects listed on bos.potlock.org). Additionally, donor requirements need to be established; by default, nada.bot verifies that donors are human through an application that allows users to verify different services to build their human score. Optional minimum donation amounts can also be set.

### 💪🏿 Pot Admin(s) - Optional

Admins are individuals designated by the owner who can perform all functions that a pot owner can do except for adding or removing other admins. They play a crucial role in managing the pot alongside the owner. This structure avoids redundancy by integrating all relevant information about the pot owner's responsibilities into one cohesive section. Let me know if you’d like any further adjustments!

### **👩🏿‍🍳 Chef**&#x20;

The chef is an appointed account responsible for approving applications, supporting donors, and collecting automated fees for donations and sponsorships. This role is crucial for ensuring that projects are vetted properly and that the funding process runs smoothly.

### **🙏 Verified Donors**&#x20;

Verified donors are individuals who confirm their humanity through nada.bot or other verification methods. Once verified, they can donate to projects during the funding round to receive matching contributions. This verification process helps maintain trust and integrity within the funding ecosystem.

### **🥯 Sponsors**&#x20;

Sponsors are individuals or entities that contribute to the entire funding round. Their logos (or NEAR social profile pictures) appear on the sponsor board. Typically, most funding comes from committed sponsors before the round begins. Sponsors serve as an alternative for those who prefer not to verify but still want to support the entire round rather than individual projects.

{% content-ref url="../../sponsors-or-funding-a-matching-round.md" %}
[sponsors-or-funding-a-matching-round.md](../../sponsors-or-funding-a-matching-round.md)
{% endcontent-ref %}

### 🏥 Projects

Projects are those applying for funding. If approved, they often onboard their network of donors to maximize their matching potential. Projects expect timely notifications regarding their application status, guidance on how to support their donors, and updates on where their funds are allocated.&#x20;

{% content-ref url="../../projects/" %}
[projects](../../projects/)
{% endcontent-ref %}
