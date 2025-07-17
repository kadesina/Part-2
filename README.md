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
3. At the bottom make sure you click on deposit $0.00 and link my credit card. 

> ⚠️ **Note:** The free credit promotion is available for **new users only** and may vary based on current offers. Be sure to check the Vultr homepage or your email for any applicable promo codes.
<img width="3394" height="1678" alt="image" src="https://github.com/user-attachments/assets/10e2c4ac-e1e6-41cc-9238-f90b97b9a7f5" />

Step 3: once you have enter your credit card information, on the left side of your dashboard, click on product s then computer then in the middle of the window click xccomuter then "Deploy Server" 

# Deploying Servers

These next step-by-step guides will show you how to install and configure a server from scratch.

I’ll walk you through the full setup process for the **first server**. Once that’s done, you can follow the **same steps** to deploy the **second server**, which will serve as our **test machine** (a Windows Server).

1. **Navigate to https://my.vultr.com/** Sign in with your credentials
2. **Click "Products"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/d3a5790b-521c-48a6-8184-95c014a9addd" />

3. **Click "Compute"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/cc4c2392-e573-4ff9-ac23-d7b6a516a523" />

4. **Click "Deploy Server"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/d8f68be4-25a2-41d8-ab87-ed506b5d03a4" />

5. **Click on Shared CPU**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/3dcdd64a-acf4-4c68-807c-6310ab48c4c1" />

6. **Click on the location closest to you mine is "New York (NJ)"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/a4fe0f92-a985-44ba-afae-bec80e324ef0" />

7. **Click "All"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/4456d968-1880-4957-9f22-7eaf2e3227d9" />

8. **Choose "vc2-2c-4gb" We dont need a alot of resources on the server**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/fcd10337-2a1e-44ac-88be-e6b64e5aae66" />

9. **Click "Configure"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/da24cad9-1b43-482e-b4b1-b1c179e84b94" />

10. **For our OS click on Windows Standard**
11. **Click the drop down and select "2022 x64**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/e7adffcc-0ec0-419f-82ac-bcdaeac016a8" />

12. **Click the "Server 1 Hostname" and give your server a name**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/6867a559-ea5d-4fd7-b142-ad3f666cc478" />

13. **Click "Automatic Backups"**
14. **Click the "Yes, I understand the risks." field.**
15. **Click on "Disable Automatic Backups" its not needed for this project**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/78d0b6ee-8fa6-4350-ae2b-962ba709e2d3" />

16. **Click on "Public IPv4" then "Deploy"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/c5a95694-07f3-4ebc-b41f-cc259639a6d6" />

17. **Once all is configured you should have your server installed and ready**
<img width="1744" height="1012" alt="image" src="https://github.com/user-attachments/assets/ca8bde34-adf4-4e70-9211-9e1b845ea775" />

## For the 2nd Server

Follow the **exact same steps** from **Step One**, but make the following change when selecting server specifications:

### Specs for the Test Server:
- **Plan:** `vc2-1c-2gb`
- **Price:** $10/month

> 📝 This configuration is lighter and more cost-effective. It’s ideal for a test machine since we don’t need high performance for this environment.

## Deploying Ubuntu server

> ⚠️ This option is lighter than the primary server because we don’t need high performance — it's strictly for testing purposes.

Keep following the same process unless otherwise noted, and you'll have both servers deployed successfully.

