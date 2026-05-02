# Password Policy Example

**Document ID**: CCF-POL-002  
**Version**: 1.0  
**Effective Date**: May 2026  
**Owner**: Chase Cooley, CoolUnderFire Cybersecurity LLC  
**Purpose**: Establish minimum standards for password creation, use, and management to protect accounts and systems.

## 1. Scope
This policy applies to all user accounts, service accounts, and administrative credentials in the lab environment, CoolUnderFire support engagements, and personal systems.

## 2. Password Requirements

### 2.1 Complexity & Length
- Minimum length: **12 characters**
- Must include at least three of the following:
  - Uppercase letters (A–Z)
  - Lowercase letters (a–z)
  - Numbers (0–9)
  - Special characters (!@#$%^&* etc.)

### 2.2 Prohibited Practices
- No common words, dictionary terms, or personal information (names, birthdays, etc.).
- No reuse of the same password across multiple systems.
- No sharing of passwords.

### 2.3 Password History & Aging
- Password history: **24** previous passwords remembered (cannot reuse).
- Maximum password age: **90 days** (forced change).
- Minimum password age: **1 day** (prevent immediate reuse).

### 2.4 Account Lockout
- Lockout after **5** consecutive failed attempts.
- Lockout duration: **15 minutes** (or until manually unlocked by admin).
- Reset counter after **15 minutes**.

### 2.5 Multi-Factor Authentication (MFA)
- MFA is **required** for all administrative accounts and remote access.
- Strongly recommended for all user accounts.

### 2.6 Password Storage & Transmission
- Passwords must never be stored in plain text.
- Use password managers for personal and client use.
- Transmit passwords securely (never via email in plain text).

## 3. Enforcement & Monitoring
- Enforced via Group Policy (Active Directory) or equivalent on non-domain systems.
- Wazuh monitoring for excessive failed login attempts.
- Quarterly password policy compliance audits.

## 4. Exceptions
- Service accounts may have longer expiration with compensating controls (e.g., complex random passwords, restricted access).
- All exceptions require written approval and documentation.

## 5. User Responsibilities
- Choose strong, unique passwords.
- Change passwords when prompted or if compromise is suspected.
- Report suspected compromise immediately.

## 6. References
- NIST SP 800-63B (Digital Identity Guidelines)
- Security+ Domain 5 (Identity and Access Management)
- Industry best practices for password security

**Approval**  
Signed: Chase Cooley
Date: May 2026

---

**Status**: Sample / Draft Policy  
**Intended Use**: Template for lab enforcement, client recommendations, and portfolio demonstration. Enforce via GPOs in the home lab.
