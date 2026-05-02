# Compliance Checklist

**Document ID**: CCF-CHK-001  
**Version**: 1.0  
**Effective Date**: May 2026  
**Owner**: Chase Cooley, CoolUnderFire Cybersecurity LLC  
**Purpose**: Quick reference checklist for maintaining basic compliance and security hygiene in the home lab and client environments.

## 1. Access Control & Identity
- [ ] Least privilege enforced (no unnecessary admin rights)
- [ ] Strong password policy active (12+ chars, complexity, history)
- [ ] Account lockout enabled (5 attempts)
- [ ] MFA enabled on administrative and remote access
- [ ] Quarterly access reviews completed
- [ ] Offboarding process (immediate disablement)

## 2. Network & Perimeter Security
- [ ] Firewall rules reviewed and documented (pfSense)
- [ ] Network segmentation / VLANs in use
- [ ] Unnecessary ports/services disabled
- [ ] Remote access logged and secured (VPN preferred)

## 3. Monitoring & Logging
- [ ] Wazuh SIEM or equivalent monitoring active
- [ ] Critical logs enabled (AD, security events, firewall)
- [ ] Alert rules tuned and tested
- [ ] Log retention policy followed

## 4. Vulnerability & Patch Management
- [ ] Regular patching schedule for OS and applications
- [ ] Vulnerability scanning performed periodically
- [ ] Snapshots/backups tested and available

## 5. Data Protection & Backup
- [ ] Sensitive data identified and protected
- [ ] Backups performed and tested (3-2-1 rule where possible)
- [ ] Encryption used for sensitive data at rest/transit

## 6. Incident Response Readiness
- [ ] IR playbook and checklist available
- [ ] Contact list and escalation paths documented
- [ ] Basic forensic tools ready (Wireshark, Volatility)

## 7. Documentation & Training
- [ ] Policies (access control, password, etc.) documented
- [ ] Risk register maintained and reviewed
- [ ] User awareness guidance provided (phishing, passwords)

## Review Frequency
- **Monthly**: Quick visual check of critical items
- **Quarterly**: Full checklist review + risk register update
- **Annually**: Comprehensive policy and playbook review

## Notes
- Mark items as N/A if not applicable to a specific client/lab setup.
- Document any exceptions with justification and compensating controls.
- Use this checklist during CoolUnderFire support engagements and lab maintenance.

---

**Last Updated**: May 2026  
**Intended Use**: Living checklist for personal lab, portfolio evidence, and client compliance support. Customize per environment.
