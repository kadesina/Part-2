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

Deplopying the Ubuntu server has the same steps as deploying the windows server, jut with stronger specs because its going to host my splunk server. 

1. **Click "Products"**
2. **Click "Compute"**
3. **Cick "+Deploy" at the top right corner**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/184153b2-07fb-426d-bb99-bd927b6ed1fd" />

4. **Click "Shared CPU"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/de65854e-eec5-4ddb-aadf-514343144c7b" />

5. **Click "location closest to you"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/dd6d996b-ac99-42f7-a768-0e9f68ae58fb" />

6. **Select Specs "vc2-4c-8gb"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/9a06b323-3fc3-44b8-8ff6-f0f121b049f8" />

7. **Click "Configure"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/95a6599f-bb01-4edd-8d78-9134e5a643d1" />

8. **Click on Ubuntu**
9. **Click select Version then "22.04x64"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/5bfb6ba8-f992-4542-b3a3-c4d410ecd625" />

10. **Click the "Server 1 Hostname" and give your server a name**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/666f7d98-eb04-45aa-b9f1-47b04aa3d58a" />

11. **Click "Automatic Backups"**
12. **Click the "Yes, I understand the risks"**
13. **Click the "Disable Automatic Backsups"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/021ba4d9-4df6-415e-8644-d8aafb1ab1a9" />

14. **Click "Deploy"**
<img width="872" height="506" alt="image" src="https://github.com/user-attachments/assets/a51d3bb4-d2b1-4805-8944-7f0c4493f7b9" />

Now that all our virtual machines have been created, it's time to tackle the **networking configuration** for all three systems.
You should have 3 machines 

> 📌 **Tip:** Be sure to take note of the **IP addresses** assigned to each machine — this will be important for connectivity, SSH, Splunk forwarding, and troubleshooting later.

## 🖧 Networking Setup for Virtual Machines

## 🔒 Step 1: Create a Firewall Group in Vultr

Before deploying any instances, the first thing to do is **create a Firewall Group** in Vultr. This helps control which ports are open or closed to your virtual machines, adding a critical layer of security.


After your rules are added, you’ll be able to **assign this firewall group** to your virtual machines during or after deployment.

1. **Click "Netwroking"**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/78b6cd80-0a92-45c1-a60b-d7055c243760" />

2. **Click "Firewall"**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/705f5016-c48d-497c-82b7-42df6fa38065" />

3. **Click "Add Firewall Group"**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/d0cc1b37-06f7-4de8-8922-7a19547240bd" />

4. **Click "Description"**
5. **Give your Firewall Group a name**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/9a5a4bfa-5c94-43dc-8a1f-4447c3c5ac18" />


> 📝 **Note:** When the Firewall Group is first created, Vultr automatically adds a default rule that allows SSH connections (**port 22**) from **anywhere (0.0.0.0/0)**.
>
> 🔒 This is a **security risk**. You should immediately **edit this rule** to restrict SSH access to **your specific IP address only**. This minimizes the chances of brute-force attacks and unauthorized access.
> 
> ✅ To find your public IP address, visit [https://whatismyipaddress.com](https://whatismyipaddress.com), then update the rule to use your IP in CIDR format (e.g., `192.0.2.1/32`).

6. **Click "Anywhere"**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/1d9b89ef-7a97-430b-80e5-360c37528b08" />

7. **Click "Custom"**
<img width="906" height="502" alt="image" src="https://github.com/user-attachments/assets/9277d6f4-1d8a-4574-9e80-54719d9f6313" />

8. **Click "x.x.x.x/xx" Add your IP address**
<img width="1812" height="1008" alt="image" src="https://github.com/user-attachments/assets/baf25186-a054-4c5f-b347-2cb0144275b8" />

9. **Configure Inbound RDP from your IP address**
10. **Click on "protocol" then select "MS RDP" the port number will automatically change to 3389**
<img width="1812" height="1006" alt="image" src="https://github.com/user-attachments/assets/78d95775-fb54-496f-bddc-42cbecaf46f6" />

11. **Click the "+" to add the rule** 
<img width="1812" height="1006" alt="image" src="https://github.com/user-attachments/assets/5135ac92-ab7f-4ce3-b1d0-bb5e929f736f" />


---

### 🔐 Now that I have my Firewall rules in place...

We've secured our **SSH** and **RDP** protocols to **only accept connections from our network** — an essential step to prevent unauthorized access.

---

### 🖥️ Adding Firewall to Virtual Machines

Once your firewall rules are in place, the next step is to assign your **virtual machines (VMs)** to the configured **Firewall Group** to ensure they inherit those protections.

Steps:

1. **Click on your Virtual Machine***
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/7f8a7da1-1322-4db7-b212-d649af253730" />

2. **Click on Settings**
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/5e466379-e5ca-488a-b813-aeb26b085afb" />

3. **Click on Firewall**
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/29e4e18b-79fc-400a-97e1-8c685e2b16fb" />

4. **Click on the Dropdown**
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/b8c70242-d8e9-412e-8bc2-dfc46c9c4810" />

5. **Click on the Firewall Group Created**
<img width="863" height="497" alt="image" src="https://github.com/user-attachments/assets/99927122-d68a-4b3a-b3e1-d109ddaa0bc5" />

6. **Click on Update Firewall Group**
<img width="863" height="506" alt="image" src="https://github.com/user-attachments/assets/629f7078-0171-49b6-ac7c-31cf5578abfc" />

### 🔁 Repeat the Process

✅ **Perform these same steps for all your virtual machines** to ensure consistent security across your entire environment.

### 🌐 Creating a VPC Network

Now I'm going to create a **VPC (Virtual Private Cloud)** network so that all my virtual machines can communicate with each other internally.

> 💡 **Note:** Each machine will have both a **public** and a **private** IP address.

1. **Click on your Virtual Machine**
<img width="863" height="506" alt="image" src="https://github.com/user-attachments/assets/47980b57-a059-48fe-8371-eff1473d2734" />

2. **Click Settings**
<img width="863" height="506" alt="image" src="https://github.com/user-attachments/assets/cfd33c77-5da2-4540-a802-2481a8904f72" />

3. **Click "VPC Networks"**
<img width="863" height="506" alt="image" src="https://github.com/user-attachments/assets/28157dfd-b91b-4dbe-a652-820adf89adf4" />

4. **Click "Enable VPC"**
<img width="863" height="506" alt="image" src="https://github.com/user-attachments/assets/e7c88f32-a703-4168-a5ba-a68bcb523701" />

> 💡 **Note:** VPC will only work in the same region as your Vm. you can't create a VPC in 2 different region

### 🔍 Testing Connectivity

The next step is to **log into my Ubuntu server** and try to **ping my test machine** to verify internal connectivity between the virtual machines.

<img width="1726" height="1012" alt="image" src="https://github.com/user-attachments/assets/10c30cdb-9424-48e6-87ce-b6b82c7cc426" />

> As you can see, there's no connectivity. Now we need to troubleshoot by checking which IP addresses are assigned to the machines.




