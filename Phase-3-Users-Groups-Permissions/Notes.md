
# Phase 3 - Users, Groups, and Permissions

## Objective

The objective of this phase was to configure and manage Active Directory objects used in a real organization.

This phase focused on:

- Creating Organizational Units (OUs)
- Creating and managing user accounts
- Creating security groups
- Assigning users to groups
- Managing computer accounts
- Joining Windows clients to the domain
- Testing authentication and access control

The purpose was to simulate how organizations manage users, computers, and permissions using Active Directory.

---

# Organizational Units (OUs)

## Overview

Organizational Units (OUs) are containers inside Active Directory used to organize users, computers, and groups.

OUs allow administrators to:

- Apply Group Policy settings
- Organize objects based on business requirements
- Delegate administrative tasks
- Manage resources efficiently

---

# Active Directory OU Structure

The Active Directory environment was reorganized into a structured design separating users, computers, and groups.

sancalab.local

├── Company Users │ │   ├── Finance │   │     └── David Brown │   │ │   ├── HR │   │     ├── Mary Jones │   │     └── Sarah Johnson │   │ │   ├── IT │   │     ├── John Smith │   │     └── Michael Smith │   │ │   └── Sales │         ├── Sarah Williams │         └── Emily Davis │ ├── Company Computers │ │   └── IT │         └── Client01 │ └── Groups │ ├── Finance │     └── Finance_Users │ ├── HR │     └── HR_Users │ ├── IT │     └── IT_Users │ └── Sales └── Sales_Users

---

# User Account Management

User accounts were created to represent employees within different departments.

## Finance Department

| Name | Username |
|---|---|
| David Brown | dbrown |

---

## HR Department

| Name | Username |
|---|---|
| Mary Jones | mjones |
| Sarah Johnson | sjohnson |

---

## IT Department

| Name | Username |
|---|---|
| John Smith | jsmith |
| Michael Smith | msmith |

---

## Sales Department

| Name | Username |
|---|---|
| Sarah Williams | swilliams |
| Emily Davis | edavis |

---

# Security Groups

## Purpose

Security groups are used to manage permissions efficiently.

Instead of assigning permissions to individual users, administrators assign permissions to groups.

Example:

Instead of assigning Finance folder access individually to every Finance employee:

- David Brown
- Future Finance employees

Access can be assigned to:

Finance_Users

Any user added to the group automatically receives the assigned permissions.

---

# Security Groups Created

| Department | Security Group |
|---|---|
| Finance | Finance_Users |
| HR | HR_Users |
| IT | IT_Users |
| Sales | Sales_Users |

---

# Group Membership

Users were assigned to security groups based on their departments.

Finance_Users └── David Brown

HR_Users ├── Mary Jones └── Sarah Johnson

IT_Users ├── John Smith └── Michael Smith

Sales_Users ├── Sarah Williams └── Emily Davis

---

# Domain Client Joining

A Windows 11 client machine was joined to the Active Directory domain.

## Client Information

| Computer | Operating System | Purpose |
|---|---|---|
| Client01 | Windows 11 | Domain Client |

---

# Domain Information

Domain:

sancalab.local

Domain login format:

SANCALAB\username

Example:

SANCALAB\David.brown

Successful login confirmed:

- Domain communication was working
- DNS resolution was working
- User authentication was successful

---

# Computer Account Management

Client01 was moved from the default computer container into the managed computer OU structure.

Current location:

Company Computers

└── IT └── Client01

This allows administrators to apply computer-based policies through Group Policy.

---

# Group Policy Management

A Group Policy Object (GPO) was created to apply security settings to domain computers.

## Created GPO

PC Security Baseline

---

# Security Setting Implemented

The following security setting was configured:

Computer Configuration

└── Policies

└── Windows Settings

    └── Security Settings

        └── Local Policies

            └── Security Options

                └── Accounts: Guest account status

                    └── Disabled

---

# Group Policy Verification

The policy was updated on the client machine using:

```cmd
gpupdate /force

The applied policies were verified using:

gpresult /scope computer /r

The PC Security Baseline policy was successfully applied to Client01.


---

Permission Management

The lab simulated company resource access using security groups.

Example:

Finance users were managed through:

Finance_Users

This demonstrates the practice of assigning permissions to groups instead of individual users.


---

Security Concepts Demonstrated

Least Privilege

Users should only receive the access required to perform their job responsibilities.

Example:

Finance users should not automatically receive IT administrative permissions.


---

Identity and Access Management (IAM)

Active Directory was used to manage:

User identities

Authentication

Authorization

Resource access



---

Troubleshooting

Domain Login Troubleshooting

Problem:

Unable to authenticate using a domain account.

Checked:

Domain name

User account

Domain Controller availability

Network connectivity

DNS configuration


Resolution:

Confirmed the correct login format:

SANCALAB\username


---

Lessons Learned

During this phase I learned:

How organizations structure Active Directory

How to manage users and computers

How security groups simplify permissions

How domain authentication works

How OU structure affects administration

How Group Policy is applied to computers

The importance of identity and access management



---

Screenshots

01 - DC01 Domain Controller

02 - Organizational Units

03 - First Active Directory User

04 - Users Created

05 - Finance Security Group

06 - Windows 11 Joined Domain

11 - Group Policy Applied Verification

12 - Guest Account Disabled by GPO

13 - GPO After OU Restructure Verification

14 - Final Active Directory OU Structure


