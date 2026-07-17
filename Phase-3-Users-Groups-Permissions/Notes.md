# Phase 3 - Users, Groups, and Permissions

## Objective

The objective of this phase was to configure Active Directory objects used in a real organization.

This included:

- Creating Organizational Units (OUs)
- Creating user accounts
- Creating security groups
- Managing permissions
- Testing domain user authentication

The purpose was to simulate how companies manage employee accounts and access to resources.

---

# Organizational Units (OUs)

## Overview

Organizational Units are containers inside Active Directory used to organize users, computers, and groups.

They allow administrators to:

- Apply Group Policies
- Organize departments
- Delegate administrative tasks
- Manage objects efficiently

---

# OU Structure Created

The following Organizational Units were created: sancalab.local, IT, PCs, Sales, HR 

---

# Why OUs Were Created

In an enterprise environment, users are separated based on departments and responsibilities.

Example:

Finance users may require access to financial resources.

IT users may require administrative permissions.

Separating objects into OUs makes management easier and improves security.

---

# User Account Creation

User accounts were created to represent employees inside the domain.

Example:

Name: David Brown

Username: David.brown

Domain: SANCALAB

Full login format: SANCALAB\David.brown

---

# Security Groups

## Purpose

Security groups are used to assign permissions to multiple users instead of configuring every user individually.

Example:

Instead of giving access to each Finance employee: David Brown Sarah Smith John Williams 

Permissions are assigned to: Finance_Users

Any member added to the group automatically receives the assigned permissions.

---

# Groups Created

Example: Finance_Users

Location: Finance OU

Purpose:

Manage access for Finance department users.

---

# Group Types Learned

During this phase, the following Active Directory group types were explored:

## Global Group

Used to organize users from the same domain who share similar responsibilities.

Example: Finance_Users

---

## Domain Local Group

Used to assign permissions to resources.

Example:

A shared folder permission group.

---

## Distribution Group

Used mainly for email communication and does not provide permissions.

---

# Domain Client Joining

A Windows 11 client machine was joined to the Active Directory domain.

Domain: sancalab.local

---

# Domain Login Testing

After joining the domain, authentication was tested using:

User: SANCALAB\David.brown

Successful login confirmed:

- Domain communication was working
- DNS resolution was working
- User authentication was successful

---

# Permission Management

The lab simulated company resource access.

Example:

Finance shared folder: Finance Shared Folder

Access was assigned through: Finance_Users

This demonstrates the principle of managing permissions through groups rather than individual accounts.

---

# Security Concepts Demonstrated

## Least Privilege

Users should only receive the access required to perform their job.

Example:

Finance users should not automatically receive IT administrator permissions.

---

## Identity and Access Management (IAM)

Active Directory was used to manage:

- User identities
- Authentication
- Authorization
- Resource access

---

# Troubleshooting

## Login Issue

Problem:

Unable to authenticate using the domain account.

Investigation:

Checked:

- Domain name
- User account
- Domain Controller availability
- Network connectivity

Resolution:

Confirmed the correct login format: SANCALAB\username

---

# Lessons Learned

During this phase I learned:

- How organizations structure Active Directory
- How users and groups are managed
- Why security groups are important
- How permissions are assigned
- How domain authentication works
- The importance of least privilege