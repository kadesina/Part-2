# ☁️ Cloud Lab Environment Setup

### 🎯 Objective
In this part of the project, I’m setting up a small virtual lab with three virtual machines. The goal is to ensure they can communicate with each other and serve as the foundation for future cybersecurity and SIEM-related configurations.

### 🧱 Virtual Machines

1. **Windows Server 1** – **Domain Controller (DC)**
   - Promoted to a Domain Controller.
   - Configured with **Active Directory Domain Services (AD DS)**.
   - Will manage domain authentication and Group Policy Objects (GPOs).

2. **Windows Server 2** – **Domain-Joined Client**
   - Joined to the domain controlled by Windows Server 1.
   - Used for testing domain communication and policy enforcement.

3. **Ubuntu Server** – **Splunk Server**
   - Serves as the central logging system using **Splunk**.
   - Will collect logs from the Windows machines for future security analysis.
### 🔑 Step 1: Create a Vultr Account

To begin setting up the cloud environment, head over to [**Vultr**](https://www.vultr.com/) and create an account.

> 📝 **Note:** You will need a **valid credit card** to verify your identity and activate your account.

Once your account is set up, you’ll have access to the Vultr dashboard where you can deploy virtual machines (instances) in just a few clicks.
<img width="1697" height="839" alt="image" src="https://github.com/user-attachments/assets/f44a794b-7417-4b70-958c-889bafc7ec0a" />

### 💳 Step 2: Add Billing Information & Claim Free Credit

After creating your Vultr account, go to the **Billing** section in your dashboard.

1. Add a **valid credit card** to verify your account.
2. If you're a **new user**, you may be eligible to receive **up to $300 in free credit** as part of Vultr's promotional offer.

> ⚠️ **Note:** The free credit promotion is available for **new users only** and may vary based on current offers. Be sure to check the Vultr homepage or your email for any applicable promo codes.
<img width="3394" height="1678" alt="image" src="https://github.com/user-attachments/assets/10e2c4ac-e1e6-41cc-9238-f90b97b9a7f5" />

### ✅ Goals
- [x] Install all three VMs.
- [x] Place all VMs on the same internal/private network.
- [x] Test network connectivity between all machines (`ping`, `tracert`, etc.).
- [x] Promote one Windows Server to a Domain Controller.
- [x] Join the second Windows Server to the domain.
- [x] Prepare the Ubuntu machine for Splunk installation (Part 4).



