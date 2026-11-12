# Vendor Risk & Procurement Framework (TPRM)

## Overview
This framework is designed to align with the supplier relationship requirements of ISO 27001:2022 and the processor obligations of GDPR Article 28.

Enterprise Third-Party Risk Management (TPRM) software is expensive and overly complex for small IT operations. This repository provides a lightweight, open-source framework to evaluate, track, and offboard vendors securely. 

This framework was built to operationalize **IT Governance**, **Regulatory Compliance**, and **Third-Party Risk Management**.

## The Framework

Before using the templates, read the **[Framework Methodology Guide](./00_Framework_Guide.md)** to understand the 4-phase lifecycle (Assess → Score → Track → Exit).

1. **[Framework Guide](./00_Framework_Guide.md):** The step-by-step methodology for managing the vendor lifecycle.
2. **[Due Diligence Questionnaire](./01_Due_Diligence_Questionnaire.md):** The pre-onboarding security assessment.
3. **[Risk Scoring Matrix](./02_Risk_Scoring_Matrix.xlsx) / ([.csv](./02_Risk_Scoring_Matrix.csv)):** Likelihood x Impact scoring. The `.xlsx` contains live formulas and dashboard formatting.
4. **[Vendor Register](./03_Vendor_Register_Template.xlsx) / ([.csv](./03_Vendor_Register_Template.csv)):** The central tracker for SLAs. The `.xlsx` contains live formulas for breach flagging.
5. **[Offboarding Checklist](./04_Offboarding_Checklist.md):** The secure exit and data destruction procedure.
6. **[Practical Use Cases](./05_Use_Cases.md):** Real-world scenarios demonstrating how to apply this framework in an enterprise.

*Note on file formats: The templates are provided in both `.xlsx` (for live Excel formulas and dashboard formatting) and `.csv` (for quick plain-text viewing in code editors like VS Code).*

## Why this exists
Many data breaches originate from third-party vendors. This framework ensures that due diligence, SLA enforcement, and secure offboarding are treated as mandatory controls, not afterthoughts. 

## 📊 Sample Output: Risk Scoring Matrix

| Vendor Name | Data Sensitivity | Breach Likelihood | Total Score | Risk Tier |
| :--- | :--- | :--- | :--- | :--- |
| HR Software | 5 | 4 | 20 | 🔴 Critical |
| AWS | 4 | 2 | 8 | 🟠 High |
| Local Cleaning | 1 | 1 | 1 | 🟢 Low |

## 📊 Sample Output: Vendor Register (SLA Tracking)

*The Excel template includes built-in formulas to compare Guaranteed vs. Delivered SLAs and automatically flag breaches (Red), passes (Green), and non-applicable metrics (Grey).*

| Vendor Name | Risk Tier | SLA Guarantee | Delivered SLA | Breach Status | Open Findings |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Cloudflare | High | 99.90% | 99.95% | 🟢 MET | 0 |
| Legacy Mail Provider | High | 99.90% | 99.50% | 🔴 BREACH | 2 |
| Local Cleaning | Low | N/A | N/A | ⚪ N/A | 0 |

## Author
Built by Piyush Gahlawat. For more of my work, see [Shiryu Kit](https://shiryu-kit.shiryu.workers.dev).