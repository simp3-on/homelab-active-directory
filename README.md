# Active Directory Homelab

A hands-on Windows Server 2022 homelab built in VMware Workstation Pro to learn Active Directory administration, Group Policy, Windows networking, and enterprise system administration.

---

## Lab Environment

| Component | Value |
|------------|---------|
| Host Machine | Lenovo ThinkPad T490s |
| RAM | 8 GB |
| Storage | 256 GB SSD |
| Hypervisor | VMware Workstation Pro |
| Server OS | Windows Server 2022 Standard (Desktop Experience) |
| Domain | simsi.local |
| Domain Controller | DC01 |

---

## Objectives

- Learn Windows Server administration
- Deploy Active Directory Domain Services (AD DS)
- Manage users and groups
- Configure Group Policy Objects (GPOs)
- Join client machines to a domain
- Implement file shares and NTFS permissions
- Automate administration with PowerShell

---

## Project Progress

### Completed

- [x] Windows Server 2022 Installation
- [x] Active Directory Domain Services (AD DS)
- [x] Domain Controller Promotion
- [x] Domain Creation (simsi.local)
- [x] Organizational Unit (OU) Creation
- [x] User Account Creation
- [x] Security Group Creation
- [x] Group Membership Management

### In Progress

- [ ] Group Policy Objects (GPOs)
- [ ] Domain-Joined Windows Client
- [ ] Shared Folders
- [ ] NTFS Permissions
- [ ] Roaming Profiles
- [ ] PowerShell Administration
- [ ] DNS Administration
- [ ] DHCP Services
- [ ] Backup and Recovery

---

## Documentation

### Phase 1 – Active Directory Deployment

- Domain Controller setup
- AD DS installation
- Domain promotion
- Organizational Units

See:

[Phase 1 Documentation](docs/phase1.md)

### Phase 2 – Users and Groups

- User creation
- Security groups
- Group membership
- OU vs Group concepts

See:

[Phase 2 Documentation](docs/phase2-users-and-groups.md)

---

## Active Directory Structure

```text
simsi.local
│
├── HR
│   ├── Mary HR
│   └── HR_Users
│
├── IT
│   ├── John Admin
│   ├── Peter Support
│   └── IT_Users
│
├── FINANCE
│   ├── David Finance
│   └── Finance_Users
│
└── SALES
    ├── Sarah Sales
    └── Sales_Users
```

---

## Skills Demonstrated

- VMware Workstation
- Windows Server Administration
- Active Directory
- Identity and Access Management (IAM)
- User and Group Management
- Organizational Unit Design
- Enterprise Network Administration

---

## Author

Simsi Jimoh

Cybersecurity Graduate | Networking & Systems Administration Enthusiast
