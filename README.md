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
  
First thing step to this is to head over to vultr.com and then sign up for an account. yyou will need a valid credit card to verify your identity.

### ✅ Goals

- [x] Install all three VMs.
- [x] Place all VMs on the same internal/private network.
- [x] Test network connectivity between all machines (`ping`, `tracert`, etc.).
- [x] Promote one Windows Server to a Domain Controller.
- [x] Join the second Windows Server to the domain.
- [x] Prepare the Ubuntu machine for Splunk installation (Part 4).

---


