# Security Audit: Controls and Compliance Checklist

## Scenario

Botium Toys is a fictional small U.S. toy company with a single physical location that serves as its main office, storefront, and warehouse. As its online sales grew to customers in the U.S. and abroad, including the E.U., the IT manager decided to run an internal IT audit. I reviewed the IT manager's audit scope, goals, and risk assessment report, then completed this checklist to identify which controls and compliance best practices the company was missing, and recommended the ones it should put in place.

## Controls assessment

Does Botium Toys currently have this control in place?

| Control | In place? |
|---|---|
| Least privilege | No |
| Disaster recovery plans | No |
| Password policies | No |
| Separation of duties | No |
| Firewall | Yes |
| Intrusion detection system (IDS) | No |
| Backups | No |
| Antivirus software | Yes |
| Manual monitoring, maintenance, and intervention for legacy systems | No |
| Encryption | No |
| Password management system | No |
| Locks (offices, storefront, warehouse) | Yes |
| Closed-circuit television (CCTV) surveillance | Yes |
| Fire detection/prevention (fire alarm, sprinkler system, etc.) | Yes |

## Compliance checklist

Does Botium Toys currently adhere to this compliance best practice?

### Payment Card Industry Data Security Standard (PCI DSS)

| Best practice | Adheres? |
|---|---|
| Only authorized users have access to customers' credit card information. | No |
| Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment. | No |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data. | No |
| Adopt secure password management policies. | No |

### General Data Protection Regulation (GDPR)

| Best practice | Adheres? |
|---|---|
| E.U. customers' data is kept private/secured. | No |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach. | Yes |
| Ensure data is properly classified and inventoried. | No |
| Enforce privacy policies, procedures, and processes to properly document and maintain data. | Yes |

### System and Organization Controls (SOC)

| Best practice | Adheres? |
|---|---|
| User access policies are established. | No |
| Sensitive data (PII/SPII) is confidential/private. | No |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated. | Yes |
| Data is available to individuals authorized to access it. | Yes |

## Recommendations

### 1. General Recommended Controls

- Install an IDS to detect potential cyberattacks earlier.
- Set up detailed disaster recovery plans and create backups of all critical data, storing the backups in secure locations that only authorized personnel can access, following the principle of least privilege.
- Establish a regular schedule to monitor and maintain legacy systems, with clear intervention methods for when issues come up.

### 2. Compliance-Required Controls (from PCI DSS, GDPR, or SOC)

- Set up and enforce policies that ensure all company data is properly classified and inventoried. - GDPR
- Implement role-based access controls that enforce the principle of least privilege and a strict separation of duties, ensuring that only personnel who require access to sensitive data for their role are authorized to access it. - PCI DSS, GDPR, and SOC
- Encrypt all customer credit card information that the company accepts, processes, transmits, and stores in its internal database to keep it confidential. - PCI DSS, GDPR, and SOC
- Strengthen the current password policy to meet PCI DSS v4.0.1 requirements (a minimum of 12 characters, with both letters and numbers). Install a secure, centralized password management system to enforce the password policy's minimum requirements and automatically manage password reset requests. - PCI DSS
