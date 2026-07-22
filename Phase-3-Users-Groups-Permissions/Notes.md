Phase 3 - User and Computer Management

Overview

In this phase, I configured the Active Directory environment by creating and organizing users, security groups, computers, and Organizational Units (OUs). I also implemented a Group Policy Object (GPO) to apply a basic security setting to domain-joined computers.

This phase focused on identity and access management, Active Directory organization, and centralized administration.

---

Objectives

- Create departmental Organizational Units (OUs)
- Create domain users
- Create security groups
- Assign users to security groups
- Join a Windows 11 client to the domain
- Organize Active Directory using a structured OU hierarchy
- Configure and verify a Group Policy Object (GPO)

---

OU Structure

sancalab.local

├── Company Users
│
│   ├── Finance
│   ├── HR
│   ├── IT
│   └── Sales
│
├── Company Computers
│
│   ├── Finance
│   ├── HR
│   ├── IT
│   └── Sales
│
└── Groups
    ├── Finance
    ├── HR
    ├── IT
    └── Sales

---

Users Created

Finance

- David Brown

HR

- Mary Jones
- Sarah Johnson

IT

- John Smith
- Michael Smith

Sales

- Sarah Williams
- Emily Davis

---

Security Groups

- Finance_Users
- HR_Users
- IT_Users
- Sales_Users

Each user was added to the appropriate departmental security group.

---

Computer Management

- Joined Client01 (Windows 11) to the "sancalab.local" domain.
- Moved Client01 into the appropriate Organizational Unit under Company Computers.

---

Group Policy Configuration

Created a Group Policy Object:

- PC Security Baseline

Configured:

- Disabled the built-in Guest account.

Verified policy deployment using:

gpupdate /force
gpresult /scope computer /r

Confirmed that the Group Policy was successfully applied to Client01.

---

Skills Demonstrated

- Active Directory Users and Computers
- Organizational Unit Management
- User Administration
- Security Group Administration
- Computer Account Management
- Domain Administration
- Group Policy Management
- Identity and Access Management (IAM)
- Windows Administration
- Troubleshooting Group Policy

---

Screenshots

- Organizational Units
- Users Created
- Finance Security Group
- Windows 11 Joined Domain
- Client01 Moved to Company Computers OU
- Group Policy Applied Verification
- Guest Account Disabled by Group Policy
- Final Active Directory OU Structure