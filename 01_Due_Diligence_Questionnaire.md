# Vendor Due Diligence Questionnaire (DDQ)

*Use this questionnaire to assess the risk of a new vendor before onboarding. Items marked **🔴 [MANDATORY]** represent the bare minimum legal and security requirements.*

**Vendor Name:** _______________________
**Assessment Date:** ____________________
**Assessor:** __________________________

---

## 1. Security Governance & Policies
- [ ] Do you have a dedicated Information Security Officer (CISO) or a security team?
- [ ] Do you maintain a formal, documented Information Security Policy approved by management?
- [ ] Do you conduct annual security awareness training and phishing simulations for all employees?
- [ ] Do you perform background checks on employees with access to sensitive data?

## 2. Access Control & Data Security
- [ ] 🔴 **[MANDATORY]** Is Multi-Factor Authentication (MFA) enforced for all remote access and administrative accounts?
- [ ] 🔴 **[MANDATORY]** Is data encrypted at rest (e.g., AES-256) and in transit (e.g., TLS 1.2+)?
- [ ] Do you enforce the Principle of Least Privilege (PoLP) for data access?
- [ ] Are administrative or privileged accounts strictly limited and monitored?
- [ ] Do you have a formal vulnerability management and patch management program?

## 3. Data Privacy & Regulatory Compliance
- [ ] 🔴 **[MANDATORY]** What categories of Personal Identifiable Information (PII) do you process on our behalf? *(If you are unsure, this is an automatic failure)*
- [ ] 🔴 **[MANDATORY]** Are you compliant with GDPR, the DPDP Act (India), or other relevant regional frameworks?
- [ ] 🔴 **[MANDATORY]** Will you sign a Data Processing Agreement (DPA) that includes standard contractual clauses?
- [ ] 🔴 **[MANDATORY]** Where is our data hosted geographically? (Specify country/region).
- [ ] How do you handle Data Subject Access Requests (DSARs) or data deletion requests?
- [ ] What is your data retention policy, and how is data securely destroyed upon contract termination?

## 4. Sub-processors & Supply Chain
- [ ] Do you use sub-processors (fourth parties) to handle or store our data?
- [ ] If yes, do you have a current list of sub-processors available for review?
- [ ] Do you flow down equivalent security and privacy requirements to your sub-processors?

## 5. Business Continuity & Disaster Recovery (BCP/DR)
- [ ] Do you have a documented Business Continuity Plan (BCP) and Disaster Recovery (DR) plan?
- [ ] What are your Recovery Time Objective (RTO) and Recovery Point Objective (RPO) targets?
- [ ] How often do you test your backup restoration and DR plans?
- [ ] What is your guaranteed uptime SLA (Service Level Agreement)?

## 6. Incident Response & Breach Notification
- [ ] Do you have a formal Incident Response Plan (IRP)?
- [ ] 🔴 **[MANDATORY]** What is your maximum notification timeline in the event of a confirmed data breach? *(Must be under 72 hours for GDPR compliance).*
- [ ] Do you have cyber liability insurance that covers data breaches?
- [ ] Will you provide a root-cause analysis (RCA) report following a major incident?

## 7. Certifications & Audits
- [ ] Do you hold a current SOC 2 Type II certification? (If yes, please attach).
- [ ] Do you hold an ISO 27001 certification? (If yes, please attach).
- [ ] 🔴 **[MANDATORY]** Do we have the right to audit your security controls (either directly or via a third-party assessment)?
- [ ] Are you willing to complete a security questionnaire annually?

## 8. Financial Viability
- [ ] Are you a profitable company? (If private, please provide recent financial statements).
- [ ] Do you have a significant concentration of revenue from a single client (vendor lock-in risk)?

---

### 🚩 Assessor's Red Flag Guide

*   **RED FLAG (Escalate & Require Risk Acceptance):** Any "No" to a **🔴 [MANDATORY]** question. This does not always mean "reject." It means the risk must be escalated to the CISO. The business must either implement a **Compensating Control** or sign a formal **Risk Acceptance** form before onboarding.
*   **YELLOW FLAG (Proceed with Caution):** No SOC 2/ISO 27001 (requires deeper audit), sub-processors used without a clear list.
*   **GREEN FLAG (Low Risk):** Current ISO 27001/SOC 2 Type II, mandatory MFA, formal DPA standard.