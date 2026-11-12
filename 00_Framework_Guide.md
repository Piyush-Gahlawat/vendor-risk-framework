# TPRM Framework Guide: The Vendor Lifecycle

This document outlines the methodology for using the templates in this repository. Third-Party Risk Management (TPRM) is not a one-time task; it is a continuous lifecycle. 

This framework operates on four distinct phases: **Assess → Score → Track → Exit.**

---

## Phase 1: Assess (Pre-Onboarding)
**Artifact:** `01_Due_Diligence_Questionnaire.md`

**When to use it:** Before a contract is signed or data is shared.
**Who uses it:** Procurement, IT Security, or GRC Analyst.

**How it works:**
1. Send the questionnaire to the prospective vendor.
2. Request supporting evidence for their answers (e.g., SOC 2 Type II report, ISO 27001 certificate, or recent penetration test).
3. Review the responses. Any vendor unable to provide basic security controls (MFA, encryption) or GDPR compliance statements should be flagged for rejection or escalated to the CISO.

---

## Phase 2: Score (Risk Tiering)
**Artifact:** `02_Risk_Scoring_Matrix.xlsx`

**When to use it:** Immediately after reviewing the Due Diligence Questionnaire.
**Who uses it:** GRC Analyst or IT Risk Manager.

**How it works:**
1. Enter the vendor's name into the matrix.
2. Assign a **Data Sensitivity** score (1-5) based on the data they will access. (1 = Public data, 5 = Highly confidential PII/Financial data).
3. Assign a **Breach Likelihood** score (1-5) based on their DDQ responses. (1 = Excellent security posture, 5 = No security controls).
4. The matrix will auto-calculate the **Risk Tier** (Low, Medium, High, Critical).
5. *Action:* Critical and High-tier vendors require stricter contract clauses (e.g., right-to-audit, strict SLAs) and more frequent reviews.

---

## Phase 3: Track (Ongoing Management)
**Artifact:** `03_Vendor_Register_Template.xlsx`

**When to use it:** As soon as the contract is signed.
**Who uses it:** Vendor Manager, IT Operations, Procurement.

**How it works:**
1. Add the vendor to the central register.
2. Record the **SLA Uptime Guarantee** and **Contract Renewal Date**.
3. **Monthly/Quarterly Review:** Check the register. Are there contracts expiring in the next 90 days? Did the vendor breach an SLA this quarter?
4. **Annual Review:** Re-verify the vendor's security posture (e.g., request an updated SOC 2 report) based on their Risk Tier.

---

## Phase 4: Exit (Offboarding)
**Artifact:** `04_Offboarding_Checklist.md`

**When to use it:** When terminating a contract or migrating to a new vendor.
**Who uses it:** IT Operations, Legal, GRC.

**How it works:**
1. Use the checklist to ensure all API keys and user accounts are revoked immediately.
2. Demand a Certificate of Destruction to prove your data has been permanently deleted from their systems.
3. Review the contract for auto-renewal clauses to ensure you do not incur unexpected fees.
4. Archive the vendor's DDQ and contract in your compliance repository for audit purposes.

---

## Roles & Responsibilities
- **Procurement:** Initiates the DDQ and handles contract negotiation.
- **GRC/IT Security:** Reviews the DDQ, assigns the Risk Tier, and conducts annual audits.
- **IT Operations:** Maintains the Vendor Register and executes the Offboarding Checklist.

---

## Fast-Tracking: The "Bare Minimum" Standard

While enterprise GRC requires thorough documentation, small teams or emergency situations sometimes require a "minimum viable compliance" approach. 

If you are onboarding a low-risk vendor quickly, or offboarding in a crisis, you do not have time to fill out every single field. 

**How to read the templates:**
Items marked with **🔴 [MANDATORY]** are the absolute bare minimum. They represent the core controls required to prevent immediate legal liability (GDPR/DPDP), data breaches, or financial loss. 
*   If a vendor answers "No" to a **🔴 [MANDATORY]** question, they must be rejected.
*   If you are offboarding, you must complete all **🔴 [MANDATORY]** steps before considering the vendor officially terminated.

---

### ⚖️ When a Vendor Fails the Bare Minimum (Risk Acceptance)
What happens if a vendor fails a **🔴 [MANDATORY]** question, but the business absolutely requires their software? 
You do not automatically reject them; you escalate. The business owner and the CISO must sign a formal **Risk Acceptance Form** acknowledging the gap. Alternatively, you can require a **Compensating Control** (e.g., if the vendor lacks MFA, you mandate that they only access your data via an IP-whitelisted VPN).

---

## ⚙️ Appendix: Excel Formula Logic & Configuration

If your spreadsheet software (like Google Sheets or LibreOffice) does not automatically calculate the logic when you open the `.xlsx` templates, you can apply the following formulas manually.

### 1. Risk Scoring Matrix (`02_Risk_Scoring_Matrix.xlsx`)

**A. Total Risk Score (Column D)**
To calculate the risk score, multiply the Data Sensitivity by the Breach Likelihood. 
*   *Formula for Cell D2:* `=B2*C2`
*   *(Drag this formula down to apply it to all rows).*

**B. Risk Tier Assignment (Column E)**
To automatically assign the Risk Tier based on the score.
*   *Formula for Cell E2:* `=IF(D2>=15, "Critical", IF(D2>=8, "High", IF(D2>=4, "Medium", "Low")))`
*   *(Drag this formula down to apply it to all rows).*

### 2. Vendor Register (`03_Vendor_Register_Template.xlsx`)

**A. SLA Breach Status (Column J)**
To automatically compare the Delivered SLA (Column I) against the Guaranteed SLA (Column H) and flag a breach.
*   *Formula for Cell J2:* `=IF(OR(H2="N/A", I2="N/A"), "N/A", IF(I2<H2, "BREACH", "MET"))`
*   *(Drag this formula down to apply it to all rows).*
*  Note: If a vendor's SLA is marked "N/A", the formula will output "N/A" to prevent false breach flags.

### 3. Conditional Formatting (The Visual Dashboard)
To make the spreadsheet look like a live dashboard, apply these color rules to the respective columns:
*   **Column C (Risk Tier):** Highlight cells containing "Critical" (Red), "High" (Orange), "Medium" (Yellow), and "Low" (Green).
*   **Column J (SLA Breach Status):** Highlight cells containing "BREACH" (Red) and "MET" (Green).
*   **Column M (Open Critical Findings):** Highlight cells with a value "Greater than 0" (Red).