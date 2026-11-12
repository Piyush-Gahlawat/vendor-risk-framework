# TPRM Framework: Practical Use Cases

This document outlines three real-world scenarios demonstrating how to apply the TPRM Framework. These use cases illustrate the interaction between Procurement, GRC, and IT Operations throughout the vendor lifecycle.

---

## Use Case 1: Onboarding a New "High-Risk" Vendor (The HR Software)
**Scenario:** The HR department wants to purchase a new cloud-based applicant tracking system (ATS). The system will process employee PII (names, addresses, salaries).

*   **Actor:** GRC Analyst
*   **Trigger:** HR submits a procurement request for the new software.
*   **Precondition:** The vendor has been selected, but no contract is signed.

**Main Flow:**
1. GRC sends the **[Due Diligence Questionnaire](./01_Due_Diligence_Questionnaire.md)** to the ATS vendor.
2. The vendor returns the DDQ, indicating they use AWS for hosting (good) but do not have an ISO 27001 certification (bad).
3. GRC inputs the vendor into the **[Risk Scoring Matrix](./02_Risk_Scoring_Matrix.xlsx)**.
    *   *Data Sensitivity:* 5 (Highly confidential PII).
    *   *Breach Likelihood:* 3 (Lacks formal certification, but has basic controls).
    *   *Total Score:* 15 (Critical Tier).
4. Because the vendor is Critical Tier, GRC mandates that a **Data Processing Agreement (DPA)** and a **Right-to-Audit clause** be added to the contract.
5. Once signed, Procurement adds the vendor to the **[Vendor Register](./03_Vendor_Register_Template.xlsx)** with a renewal date of 1 year.

**Postcondition:** The vendor is onboarded with the appropriate legal and security safeguards.

---

## Use Case 2: The Annual Review of a "Critical" Vendor
**Scenario:** An existing payroll provider (Critical Tier) has been in the Vendor Register for 11 months.

*   **Actor:** IT Manager
*   **Trigger:** The **[Vendor Register](./03_Vendor_Register_Template.xlsx)** flags that the contract renewal is in 30 days.
*   **Precondition:** The vendor is actively processing payroll and holding sensitive data.

**Main Flow:**
1. IT Manager checks the Vendor Register to review the vendor's historical performance.
2. IT Manager notes that the vendor experienced two brief outages this year, but remained within the 99.9% SLA guarantee.
3. Because the vendor is Critical Tier, IT Manager requests the vendor's updated SOC 2 Type II report for the current year.
4. The vendor provides the report. IT Manager verifies there are no critical exceptions.
5. Procurement initiates the renewal contract, leveraging the Vendor Register data to negotiate a 5% discount based on the annual spend.

**Postcondition:** The vendor is renewed securely, and the Register is updated with the new contract dates.

---

## Use Case 3: Emergency Offboarding (The Data Breach)
**Scenario:** A cloud storage vendor suffers a data breach, and the company decides to terminate the contract immediately.

*   **Actor:** IT Security Lead / GRC Analyst
*   **Trigger:** A public news report or vendor notification indicating a security breach.
*   **Precondition:** The vendor has active API keys and holds company files.

**Main Flow:**
1. GRC Analyst opens the **[Vendor Register](./03_Vendor_Register_Template.xlsx)** to confirm the contract details and risk tier.
2. IT Security immediately executes the **[Offboarding Checklist](./04_Offboarding_Checklist.md)**.
3. *Access Revocation:* IT Security rotates all API keys and disables the vendor's SSO access.
4. *Data Handling:* GRC demands a Certificate of Destruction from the vendor.
5. *Financial/Legal:* Legal reviews the contract to ensure no early termination fees apply due to the vendor's breach of SLA.
6. Procurement removes the vendor from the active Vendor Register and archives the documents for the audit trail.

**Postcondition:** Access is revoked, data is confirmed destroyed, and the risk is eliminated.