# Active Directory Homelab - Phase 1

## Overview

This lab was created using:

- Host Machine: Lenovo ThinkPad T490s
- RAM: 8 GB
- Storage: 256 GB SSD
- Hypervisor: VMware Workstation Pro
- Guest OS: Windows Server 2022 Standard (Desktop Experience)

## Objective

Build a basic Windows Server environment and deploy Active Directory Domain Services (AD DS) to simulate a real-world enterprise network.

## What is Active Directory?

Active Directory (AD) is Microsoft's directory service used to centrally manage:

- Users
- Computers
- Groups
- Authentication
- Authorization
- Group Policies

Instead of managing every computer individually, administrators manage everything from a central server known as a Domain Controller (DC).

---

## Step 1: Create the Virtual Machine

A new virtual machine was created in VMware Workstation Pro.

### VM Configuration

| Setting | Value |
|----------|----------|
| Name | DC01 |
| OS | Windows Server 2022 |
| RAM | 4 GB |
| CPU | 2 vCPUs |
| Disk | 40 GB |

---

## Step 2: Install Windows Server 2022

Installed:

```text
Windows Server 2022 Standard (Desktop Experience)
```

### Why Desktop Experience?

Desktop Experience provides a graphical user interface (GUI), making administration easier while learning.

The alternative is Server Core, which is managed primarily through PowerShell and command line tools.

---

## Step 3: Install Active Directory Domain Services (AD DS)

From:

```text
Server Manager
→ Manage
→ Add Roles and Features
```

Installed:

```text
Active Directory Domain Services
```

### What is AD DS?

AD DS is the server role responsible for:

- User authentication
- User management
- Computer management
- Domain management
- Group Policy management

Installing AD DS prepares the server to become a Domain Controller.

---

## Step 4: Promote the Server to a Domain Controller

After AD DS installation:

```text
Server Manager
→ Notifications Flag
→ Promote this server to a domain controller
```

Created a new forest:

```text
simsi.local
```

### Domain

A domain is a logical administrative boundary.

Example:

```text
simsi.local
```

All users, computers, and policies belong to this domain.

### Forest

A forest is the top-level Active Directory structure.

```text
Forest
└── simsi.local
```

---

## Step 5: Verify Active Directory

Opened:

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
```

Verified that:

```text
simsi.local
```

was successfully created.

---

## Step 6: Create Organizational Units (OUs)

Created:

```text
simsi.local
├── HR
├── IT
├── FINANCE
└── SALES
```

### What is an Organizational Unit (OU)?

An OU is a container used to organize Active Directory objects such as:

- Users
- Computers
- Groups

### Why OUs Matter

OUs allow administrators to:

- Organize resources
- Apply Group Policies
- Delegate administrative control

---

## OUs vs Security Groups

### Organizational Units

Used for:

- Organization
- Group Policy targeting
- Administrative delegation

Example:

```text
IT OU
├── John
├── Peter
```

### Security Groups

Used for:

- Permissions
- Access control

Example:

```text
John
   ↓
IT_Users Group
   ↓
IT Shared Folder
```

Rule of thumb:

```text
OUs = Organization and Policy

Groups = Permissions and Access
```

---

## Current Active Directory Structure

```text
simsi.local
├── Builtin
├── Computers
├── Domain Controllers
├── ForeignSecurityPrincipals
├── Users
│
├── HR
├── IT
├── FINANCE
└── SALES
```

---

## Skills Practiced

- VMware Workstation administration
- Windows Server installation
- Active Directory Domain Services deployment
- Domain Controller promotion
- Domain creation
- Active Directory navigation
- Organizational Unit creation
- Active Directory structure design

---

## Next Phase

- Create users
- Create security groups
- Manage group membership
- Configure Group Policy Objects (GPOs)
- Join domain clients
- Configure file shares and NTFS permissions
- Learn PowerShell administration

---

## Key Takeaway

A Windows Server 2022 Domain Controller was successfully deployed and configured with Active Directory Domain Services. A new Active Directory forest and domain (`simsi.local`) was created, and departmental Organizational Units were established to provide the foundation for centralized identity and policy management.
