# Phase 4 - Security Hardening

## Objective

The objective of this phase was to improve the security posture of the Active Directory environment by implementing security controls through Group Policy.

This phase focused on:

- Password security
- Account protection
- Security auditing
- Group Policy management
- Event log investigation

The purpose was to simulate common security configurations used in enterprise Windows environments.

---

# Security Baseline Group Policy

## Overview

A new Group Policy Object (GPO) was created to apply security-related settings to domain computers.

GPO Created: Security Baseline 
The GPO was linked to: Company Computers OU

This allows security settings to be centrally managed across domain-joined computers.

---

# Password Policy Configuration

## Overview

Password policies control how users create and manage passwords within the Active Directory domain.

The policy was configured in: Default Domain Policy > Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy


---

## Password Settings Applied

| Setting | Configuration |
|---|---|
| Minimum password length | 12 characters |
| Password complexity requirements | Enabled |
| Enforce password history | 24 passwords remembered |
| Maximum password age | 60 days |
| Minimum password age | 1 day |

---

# Account Lockout Policy

## Overview

Account lockout policies help protect user accounts against brute-force password attacks.

The policy was configured in: Account Policies > Account Lockout Policy

---

## Account Lockout Settings Applied

| Setting | Configuration |
|---|---|
| Account lockout threshold | 5 invalid logon attempts |
| Account lockout duration | 15 minutes |
| Reset account lockout counter after | 15 minutes |

---

# Security Auditing

## Overview

Auditing was enabled to record security-related activities on domain computers.

Audit logs provide evidence for investigating:

- User logins
- Failed authentication attempts
- Account changes
- Security group modifications

---

# Advanced Audit Policy Configuration

Configured under: Security Baseline GPO > Computer Configuration > Policies > Windows Settings > Security Settings > Advanced Audit Policy Configuration > Audit Policies

---

# Audit Settings Configured

## Audit Logon

Enabled:

- Success
- Failure

Purpose:

Records successful and failed user authentication attempts.

Example: Event ID 4624 - Successful logon Event ID 4625 - Failed logon


---

## Audit Account Lockout

Enabled:

- Success

Purpose:

Records when accounts are locked due to failed authentication attempts.

---

## Audit User Account Management

Enabled:

- Success
- Failure

Purpose:

Tracks changes to user accounts.

Examples:

- User creation
- Password changes
- Account modifications

---

## Audit Security Group Management

Enabled:

- Success
- Failure

Purpose:

Tracks changes to security groups.

Example:

Monitoring when users are added or removed from groups.

---

# Group Policy Verification

After configuring the Security Baseline GPO, the policy was updated on Client01.

Command used: gpupdate /force
The applied policies were verified using: gpresult /scope computer /r

Verification confirmed: Security Baseline
was successfully applied to Client01.