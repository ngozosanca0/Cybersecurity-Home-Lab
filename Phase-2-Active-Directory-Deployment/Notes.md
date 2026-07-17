# Phase 2 - Active Directory Deployment

## Objective

The objective of this phase was to configure Windows Server as a Domain Controller and create an Active Directory environment.

The goal was to simulate how organizations manage users, computers, authentication, and resources through Active Directory Domain Services.

---

# Windows Server Configuration

## Server Name

The Windows Server virtual machine was configured with the hostname: sancalab.local

This created the first domain controller for the environment.

---

# Domain Information

Domain: sancalab.local

Domain Controller: DC01

Domain Administrator Account: SANCALAB\Administrator

---

# DNS Configuration

Active Directory depends on DNS for locating domain services.

DNS allows computers to find:

- Domain Controllers
- Authentication services
- Network resources

DNS was installed automatically during Domain Controller promotion.

Important DNS zones created:

- Forward Lookup Zones
- _msdcs.sancalab.local

The following records were observed:

- _tcp
- _udp
- _sites
- Domain Controller records

---

# Static IP Configuration

The Domain Controller was configured with a static IP address.

Configuration:

IP Address: 192.168.10.10

Reason:

A Domain Controller must have a predictable address because DNS and authentication services depend on consistent network communication.

---

# Active Directory Structure

After deployment, Active Directory Users and Computers was used to manage:

- Users
- Computers
- Organizational Units
- Security Groups

Initial organizational structure was created to simulate a company environment.

---

# Organizational Units Created

Organizational Units (OUs) were created to organize users and computers.

Purpose of OUs:

- Apply Group Policies
- Organize departments
- Simplify administration

Examples: Finance IT ForeignSecurity

---

# Users Created

User accounts were created to simulate employees.

Example: David Brown

Username: David.brown

The account was later used to test domain login functionality.

---

# Security Groups

Security groups were created to manage permissions.

Example: Finance_Users

Purpose:

Instead of assigning permissions individually to users, groups allow administrators to manage access more efficiently.

---

# Troubleshooting

## Domain Join Issue

Problem:

A Windows client initially could not locate the domain: An Active Directory Domain Controller for the domain sancalab.local could not be contacted.

Cause:

DNS communication issue.

Active Directory relies on DNS to locate the Domain Controller.

---

## Resolution

Troubleshooting steps performed:

- Verified Domain Controller was running
- Checked DNS service status
- Confirmed AD DS services were running
- Verified network configuration
- Corrected DNS settings

After troubleshooting, the client successfully joined: sancalab.local

---

# Lessons Learned

During this phase I learned:

- How Active Directory works
- How to deploy a Domain Controller
- The relationship between DNS and Active Directory
- How domains authenticate users
- How OUs and groups improve administration
- How to troubleshoot domain communication issues