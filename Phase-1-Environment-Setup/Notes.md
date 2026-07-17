# Phase 1 - Environment Setup

## Objective

The objective of this phase was to create a virtual environment that simulates a small enterprise network.

This lab was created using Oracle VirtualBox to safely practice Windows Server administration, Active Directory, networking, and cybersecurity concepts.

---

# Virtualization Platform

## Software Used

Oracle VirtualBox

Virtualization allows multiple operating systems to run on one physical computer.

In this project, VirtualBox was used to create:

- A Windows Server machine acting as a Domain Controller
- A Windows 11 machine acting as a company workstation

---

# Host Machine Specifications

The physical computer used for this lab:

- Operating System: Windows 11
- Processor: Intel Core i5 11th Generation
- RAM: 16GB
- Available Storage: 477GB

These resources were used to run multiple virtual machines for testing.

---

# Virtual Machines Created

## DC01 - Domain Controller

Operating System:

Windows Server 2022

Purpose:

DC01 is the central server in the lab environment.

Responsibilities:

- Active Directory Domain Services
- DNS Services
- User authentication
- Domain management


## Client01 - Workstation

Operating System:

Windows 11

Purpose:

Client01 represents an employee computer inside the organization.

Responsibilities:

- Domain login testing
- User access testing
- Group Policy testing

---

# Network Design

The lab uses a private virtual network to simulate an enterprise environment.

Network: 

192.168.10.0/24

## IP Address Allocation

| Device | IP Address | Purpose |
|---|---|---|
| DC01 | 192.168.10.10 | Domain Controller |
| Client01 | 192.168.10.20 | Domain Client |

---

# Static IP Configuration

DC01 was configured with a static IP address.

Reason:

Active Directory depends heavily on DNS. A Domain Controller must always be reachable at the same address so that client computers can locate:

- Domain services
- DNS records
- Authentication services

If the IP address changes, domain communication can fail.

---

# Problems Encountered

## Windows 11 Installation Requirements

Problem:

The Windows 11 virtual machine failed installation because it did not meet hardware requirements.

Errors encountered:

- TPM 2.0 requirement
- Secure Boot requirement

Solution:

Adjusted VirtualBox settings to support Windows 11 installation.

---

## VirtualBox Boot Problem

Problem:

The virtual machine failed to boot correctly.

Cause:

Incorrect boot order and EFI configuration.

Solution:

Disabled EFI mode and corrected the boot configuration settings.

---

# Lessons Learned

During this phase I learned:

- How virtualization works
- How to create test environments
- Basic network planning
- Importance of static IP addresses for servers
- Troubleshooting virtual machine problems
