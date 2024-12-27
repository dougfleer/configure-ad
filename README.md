<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used</h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

1. Prepare Azure Infrastructure (Create VMs, Set Networking).
2. Deploy and Promote a Domain Controller.
3. Configure Active Directory Users and OUs.
4. Join Client Machines to the Domain.

<h2>Deployment and Configuration Steps</h2>

### Step 1: Prepare Azure Infrastructure
1. **Create a Resource Group**:
   - Navigate to the Azure portal and create a new resource group for the lab.
2. **Set Up a Virtual Network**:
   - Create a virtual network and subnet to enable communication between VMs.
3. **Create VMs**:
   - Deploy a Windows Server 2022 VM named "DC-1".
   - Deploy a Windows 10 VM named "Client-1".
   - Assign both VMs to the same virtual network and set static IPs.

### Step 2: Deploy and Promote a Domain Controller
1. Log into "DC-1" and install the **Active Directory Domain Services** role.
2. Promote "DC-1" to a domain controller by creating a new forest (e.g., `mydomain.com`).
3. Restart the VM and log in with the newly created domain admin credentials.

### Step 3: Configure Active Directory Users and OUs
1. Open **Active Directory Users and Computers (ADUC)**.
2. Create Organizational Units (OUs):
   - `_EMPLOYEES` for regular users.
   - `_ADMINS` for administrative users.
3. Create user accounts:
   - Example: `jane_admin` (Domain Admin).
   - Add `jane_admin` to the Domain Admins security group.

### Step 4: Join Client Machines to the Domain
1. Configure "Client-1" to use "DC-1" as its DNS server.
2. Join "Client-1" to the domain (e.g., `mydomain.com`).
3. Restart the VM and log in using domain credentials.

By following this guide, you will have successfully implemented on-premises Active Directory in Azure. This lab demonstrates expertise in cloud infrastructure, directory services, and domain management.
