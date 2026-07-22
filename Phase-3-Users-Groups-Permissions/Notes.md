# Phase 3 - User and Computer Management

## Overview

In this phase, I configured the Active Directory environment by creating and organizing users, security groups, computers, and Organizational Units (OUs). I also implemented a Group Policy Object (GPO) to apply a basic security setting to domain-joined computers.

This phase focused on identity and access management, Active Directory organization, and centralized administration.

---

## Objectives

- Create departmental Organizational Units (OUs)
- Create domain users
- Create security groups
- Assign users to security groups
- Join a Windows 11 client to the domain
- Organize Active Directory using a structured OU hierarchy
- Configure and verify a Group Policy Object (GPO)

---

## OU Structure

```text
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