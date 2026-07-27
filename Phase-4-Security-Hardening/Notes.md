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

# Event Viewer Investigation

Windows Security logs were reviewed using:

```
Event Viewer

Windows Logs
└── Security
```

The Security log was used to investigate authentication-related events generated during testing.

---

# Security Event Testing

A failed authentication attempt was generated and investigated.

The Security log was filtered using:

```
4625
```

to identify failed logon events.

Example findings:

```
Event ID: 4625

Account Name: Client01$

Failure Reason: Unknown user name or bad password

Logon Type: 2 (Interactive)
```

---

# Security Concepts Demonstrated

## Defense in Depth

Multiple security controls were implemented, including:

- Strong password requirements
- Account lockout protection
- Windows security auditing
- Group Policy enforcement

---

## Identity and Access Management (IAM)

Active Directory was used to manage:

- User identities
- Authentication
- Authorization
- Access control

---

## Security Monitoring

Windows auditing was configured to generate security events for authentication and account management activities.

These events can be reviewed in Event Viewer or forwarded to centralized monitoring platforms such as Microsoft Sentinel, Splunk, Wazuh, or other SIEM solutions.

---

# Lessons Learned

During this phase I learned:

- How Group Policy can enforce security settings across domain-joined computers
- How password policies strengthen account security
- How account lockout policies help mitigate brute-force attacks
- How Windows auditing generates security events for investigation
- How Event Viewer can be used to analyse authentication events
- The importance of centralized log collection and security monitoring

---

# Screenshots

- 07 - Security Baseline GPO Created
- 08 - Security Baseline Linked to Company Computers
- 09 - Password Policy Configuration
- 10 - Account Lockout Policy Configuration
- 11 - Advanced Audit Policy Configuration
- 12 - Security Baseline Applied (gpresult)
- 13 - Event Viewer Security Log
- 14 - Event ID 4625 Failed Logon Investigation