# Vendor Offboarding & Exit Checklist

*Ensure that all data, access, and financial obligations are securely handled when terminating a vendor relationship. Items marked **🔴 [MANDATORY]** must be completed to prevent immediate security breaches or legal liability.*

**Vendor Name:** _______________________
**Offboarding Date:** ____________________
**Reason for Exit:** [ ] Contract Expiry | [ ] Cost Savings | [ ] Security Breach | [ ] Performance Failure
**Offboarding Lead:** ___________________

---

## 1. Transition Planning & Communication
- [ ] Notify internal stakeholders (IT, Legal, Procurement, Business Owners) of the termination.
- [ ] Confirm the official contract end date and review exit clauses.
- [ ] Establish a data migration or replacement vendor timeline.

## 2. Access & Asset Revocation (Security)
- [ ] 🔴 **[MANDATORY]** Revoke all API keys, OAuth tokens, and integration access.
- [ ] 🔴 **[MANDATORY]** Disable user accounts, SSO access, and VPN credentials for vendor personnel.
- [ ] 🔴 **[MANDATORY]** Update all internal shared passwords (e.g., admin portals) that the vendor had access to.
- [ ] Reclaim or decommission any physical hardware, access badges, or licenses provided to the vendor.
- [ ] Verify zero active vendor connections in the network/firewall logs.

## 3. Data Handling & Secure Destruction (Privacy)
- [ ] 🔴 **[MANDATORY]** Export all necessary company data from the vendor's system into a secure internal repository.
- [ ] Verify the integrity of the exported data (ensure no records are missing or corrupted).
- [ ] 🔴 **[MANDATORY]** Request a formal **Certificate of Destruction (CoD)** confirming all company data has been permanently deleted.
- [ ] Request written confirmation that company data has been purged from the vendor's backup systems and DR environments.
- [ ] Update the internal **ROPA (Record of Processing Activities)** to remove the vendor as a sub-processor.

## 4. Financial & Legal Close-Out
- [ ] Conduct final invoice reconciliation (ensure no unauthorized charges or lingering fees).
- [ ] 🔴 **[MANDATORY]** Confirm in writing that no auto-renewal clauses have been triggered.
- [ ] Retrieve and securely destroy any physical or digital confidential documents (NDAs, proprietary data).
- [ ] Process any SLA breach penalties or credits owed by the vendor before final payment.

## 5. Post-Offboarding Governance
- [ ] Update the **Vendor Register** to mark the vendor as "Inactive/Offboarded."
- [ ] Archive all vendor documentation (DDQ, Contracts, CoD) in the compliance repository.
- [ ] Revoke vendor access to any shared GRC or ticketing systems (e.g., Jira, ServiceNow).
- [ ] Conduct a post-mortem review to document lessons learned for future vendor selection.

---

### 🚩 Critical Offboarding Scenarios

**Scenario A: Contract Expiry (Low Risk)**
*   **Focus:** Smooth transition and data portability.
*   **Action:** Ensure final invoicing is accurate and data export is verified before termination. The vendor is cooperative.

**Scenario B: Cost Savings / Consolidation (Medium Risk)**
*   **Focus:** Migration timelines and overlap.
*   **Action:** Ensure the new vendor is fully operational before revoking access to the old vendor. Watch out for early termination penalties.

**Scenario C: Security Breach / Performance Failure (Critical Risk)**
*   **Focus:** Immediate containment and legal recourse.
*   **Action:** *Do not wait.* Revoke access immediately. Demand the Certificate of Destruction urgently. Involve Legal to invoke SLA penalties and withhold final payment. Preserve all logs for potential litigation.