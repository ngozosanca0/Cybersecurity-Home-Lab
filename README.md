# Cybersecurity-Home-Lab
Hands-on Active Directory, Windows Server and Cybersecurity Home Lab.

# Cybersecurity Home Lab

## Overview

This project documents the design, configuration, troubleshooting, and security testing of a virtual enterprise-style environment.

The purpose of this lab is to gain practical experience with:

- Windows Server Administration
- Active Directory Domain Services (AD DS)
- DNS
- DHCP
- Organizational Units (OUs)
- Security Groups
- Group Policy Objects (GPO)
- Windows Client Domain Joining
- User and Permission Management
- Security Monitoring and Incident Investigation

This lab is designed to simulate a small business environment and demonstrate hands-on skills relevant to IT Support, System Administration, and Cybersecurity roles.

---

# Lab Objectives

The goals of this project are:

- Build a Windows Server domain controller
- Configure Active Directory
- Create users, groups, and organizational units
- Join Windows clients to the domain
- Implement access control and permissions
- Practice troubleshooting common enterprise issues
- Document technical processes and solutions

---

# Lab Environment

## Virtualization Platform

- Oracle VirtualBox

## Host Machine

- Operating System: Windows 11
- Processor: Intel Core i5 11th Generation
- RAM: 16GB
- Storage: 477GB available space

## Virtual Machines

| Machine | Operating System | Purpose |
|---|---|---|
| DC01 | Windows Server 2022 | Domain Controller |
| Client01 | Windows 11 | Domain Client |

---

# Network Design

| Device | IP Address | Role |
|---|---|---|
| DC01 | 192.168.10.10 | Domain Controller / DNS Server |
| Client01 | 192.168.10.20 | Domain Client |

Domain Name:
- sancalab.local

### Systems

| Computer | Role |
|----------|------|
| DC01 | Domain Controller |
| CLIENT01 | Domain-Joined Client |

---

## Skills Demonstrated

- Windows Server 2022 Administration
- Active Directory Domain Services (AD DS)
- Organizational Units (OUs)
- User and Security Group Management
- DNS Configuration
- Windows 11 Domain Join
- VirtualBox Administration
- Network Troubleshooting
- DNS Troubleshooting

---

## Current Progress

✅ Windows Server installed

✅ Active Directory installed

✅ Domain Controller promoted

✅ Domain created (sancalab.local)

✅ Organizational Units created

✅ Users created

✅ Security Groups created

✅ Windows 11 client deployed

✅ Windows 11 joined to the domain

✅ DNS troubleshooting completed

---

This project will continue to grow as I add:

- Group Policy (GPO)
- File Server
- NTFS Permissions
- DHCP
- PowerShell
- Security Monitoring



---

# Project Phases

## Phase 1 - Environment Setup

- VirtualBox installation
- Virtual machine creation
- Operating system installation
- Network configuration

## Phase 2 - Active Directory Deployment

- Installing Active Directory Domain Services
- Promoting Windows Server to Domain Controller
- Configuring DNS
- Creating domain structure

## Phase 3 - User and Computer Management

- Creating Organizational Units
- Creating users
- Creating security groups
- Joining clients to domain

## Phase 4 - Security Hardening

- Group Policy implementation
- Permissions management
- Logging and monitoring

## Phase 5 - Security Investigation

- Event Viewer analysis
- Authentication troubleshooting
- SIEM integration

---

# Skills Demonstrated

- Active Directory Administration
- Windows Server Management
- DNS Troubleshooting
- Identity and Access Management
- User Administration
- Security Fundamentals
- Technical Documentation

