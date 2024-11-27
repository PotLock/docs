---
description: >-
  Deploying a pot involves several steps within the Potlock ecosystem, which
  facilitates quadratic funding rounds.
---

# 👨‍💻 Deploy Pot

{% embed url="https://youtu.be/nsI2b4qHkvE?si=vxzMEQgPRBXlwQt_" %}
Deploy Pot
{% endembed %}

### **Access the Pot Factory**:

Navigate to the Potlock decentralized front end at [https://alpha.potlock.org](https://alpha.potlock.org) and find the "Pots" tab. This is where you can deploy a pot.

### **Understand What a Pot Is**:

A pot is essentially a quadratic funding contract that allows for funding rounds to be deployed from the factory contract. It enables permissionless deployment of other contracts.

### **Initiate Deployment**

Click on "Deploy Pot." The owner (the person logged in) pays 4.4 NEAR to create an independent pot contract. It’s advisable for the owner to negotiate with sponsors beforehand to secure funding commitments.

### **Roles in Deployment**

The owner appoints a chef, who is the subject matter expert responsible for reviewing applications and initiating payouts. An admin can perform all functions of an owner except adding or removing other admins.

### **Set Parameters**

During deployment, the owner can set various parameters, including:

* Application start and end dates
* Matching round start and end dates
* Minimum and maximum donation amounts
* Fees associated with donations and sponsorships
* Note that certain parameters, like the pot's name and description, cannot be changed after deployment.

### **Human Verification**:

To prevent Sybil attacks (where individuals create multiple accounts to manipulate funding), human verification is required through nada.bot. This ensures that only verified individuals can donate.

{% content-ref url="../../products/nada.bot.md" %}
[nada.bot.md](../../products/nada.bot.md)
{% endcontent-ref %}

### **Funding Process**:

Donations made during the matching round are logged in the pot contract but are passed directly to approved projects. The actual money in the pot is used for payouts at the end of the matching round.



### **Payouts**

After the matching round concludes, there is a cooldown period during which calculations for payouts are made off-chain to ensure accuracy. Stakeholders can challenge any discrepancies during this time.



### **Final Steps**:

Once all challenges are resolved, payouts can be initiated, distributing funds to eligible projects based on their matched donations.

### **Ongoing Management**

After deployment, it’s crucial for the chef to manage marketing efforts and ensure timely onboarding of projects and donors.
