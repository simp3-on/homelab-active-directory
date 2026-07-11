# Active Directory Homelab - Phase 2
# User and Group Management

## Overview

This phase focused on creating Active Directory user accounts, creating security groups, and assigning users to the appropriate groups.

These tasks form the foundation of identity and access management in a Windows domain environment.

---

## Objective

Learn how Active Directory manages:

- User accounts
- Security groups
- Group membership
- Department-based organization

Understand why permissions should be assigned to groups rather than directly to users.

---

## Existing Environment

| Component | Value |
|------------|---------|
| Domain | simsi.local |
| Domain Controller | DC01 |
| Active Directory | Active Directory Domain Services (AD DS) |
| Departments | HR, IT, FINANCE, SALES |

---

## Step 1: Create User Accounts

User accounts were created inside their respective Organizational Units (OUs).

### IT Department

| Name | Username |
|---------|---------|
| John Admin | john.admin |
| Peter Support | peter.support |

### HR Department

| Name | Username |
|---------|---------|
| Mary HR | mary.hr |

### Finance Department

| Name | Username |
|---------|---------|
| David Finance | david.finance |

### Sales Department

| Name | Username |
|---------|---------|
| Sarah Sales | sarah.sales |

---

## What is a User Account?

A user account represents an individual identity within Active Directory.

User accounts are used for:

- Authentication
- Authorization
- Resource access
- Policy application

Examples:

```text
john.admin@simsi.local

mary.hr@simsi.local
```

---

## Step 2: Create Security Groups

Security groups were created within each department.

### Groups Created

| Department | Security Group |
|------------|---------------|
| IT | IT_Users |
| HR | HR_Users |
| FINANCE | Finance_Users |
| SALES | Sales_Users |

Group Configuration:

```text
Group Scope: Global
Group Type: Security
```

---

## What is a Security Group?

A security group is an Active Directory object used to manage permissions and access control.

Instead of assigning permissions directly to users, administrators assign permissions to groups and then add users to those groups.

Benefits:

- Easier administration
- Simplified permission management
- Better scalability
- Reduced configuration errors

---

## Step 3: Add Users to Groups

Users were assigned to their departmental security groups.

### Memberships

```text
IT_Users
├── John Admin
└── Peter Support

HR_Users
└── Mary HR

Finance_Users
└── David Finance

Sales_Users
└── Sarah Sales
```

---

## Why Use Groups Instead of Direct User Permissions?

Without groups:

```text
John Admin
    ↓
IT Shared Folder

Peter Support
    ↓
IT Shared Folder
```

Every user would need permissions assigned individually.

With groups:

```text
John Admin
Peter Support
       ↓
    IT_Users
       ↓
 IT Shared Folder
```

Administrators only manage the group.

This model is significantly easier to maintain in large environments.

---

## Understanding OUs vs Groups

One of the most important Active Directory concepts is understanding the difference between Organizational Units and Security Groups.

### Organizational Units (OUs)

Used for:

- Organization
- Group Policy targeting
- Administrative delegation

Example:

```text
IT
├── John Admin
├── Peter Support
└── IT_Users
```

### Security Groups

Used for:

- Permissions
- Resource access
- Access control

Example:

```text
IT_Users
├── John Admin
└── Peter Support
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

## Skills Practiced

- Active Directory user creation
- User account management
- Security group creation
- Group membership management
- Organizational Unit administration
- Identity and Access Management (IAM)
- Active Directory administration

---

## Key Takeaways

- User accounts represent identities within the domain.
- Security groups simplify permission management.
- Users should be assigned to groups rather than receiving permissions directly.
- Organizational Units and Security Groups serve different purposes.
- Active Directory enables centralized identity and access management across an enterprise environment.

---

## Next Phase

Phase 3 will focus on:

- Group Policy Objects (GPOs)
- Policy creation
- Policy linking
- OU targeting
- Centralized desktop and user configuration
