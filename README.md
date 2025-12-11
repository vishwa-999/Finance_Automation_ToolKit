<div align="center">

# 🚀 Agency Finance Automation Engine
### Automated Financial Control, Media Reconciliation & Strategic Unit Economics

![Python](https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![PowerBI](https://img.shields.io/badge/Power%20BI-Dashboarding-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Xero](https://img.shields.io/badge/Xero-API%20Integration-13b5ea?style=for-the-badge)
![Finance](https://img.shields.io/badge/Finance-Reconciliation%20%26%20Control-green?style=for-the-badge)

</div>

---

## 📋 Table of Contents
- [Executive Summary](#-executive-summary)
- [The Business Problem](#-the-business-problem)
- [The Solution Architecture](#-the-solution-architecture)
- [Module 1: Media Spend Reconciliation](#-module-1-media-spend-reconciliation)
- [Module 2: Strategic Squad Economics](#-module-2-strategic-squad-economics)
- [Technical Implementation](#-technical-implementation)
- [About the Author](#-about-the-author)

---

## 💼 Executive Summary

**Role Target:** Finance Manager / Financial Controller  
**Industry Focus:** High-Growth Agencies, Tech, Professional Services

This project demonstrates a **Financial Engineering** approach to solving the chaotic data problems typical in scaling agencies. By bridging the gap between **Accounting Principles (GAAP/IFRS)** and **Data Automation**, this toolset eliminates manual error, ensures 100% audit readiness, and provides real-time strategic visibility into unit profitability.

**Key Capabilities Demonstrated:**
* **Financial Control:** Automated detection of missing invoices and ledger variances.
* **Cash Flow Management:** Mitigation of "Float Risk" in media buying.
* **Strategic FP&A:** Granular profitability analysis per business unit (Squad).

---

## 🔻 The Business Problem

Scaling agencies face a "Data Disconnect" that threatens margins:
1.  **Messy Data:** Marketing platforms (Facebook/Google Ads) generate millions of transaction rows that don't match the Accounting Ledger (Xero/QuickBooks).
2.  **Liability Risk:** Client funds for ad spend often get mixed with operational cash, creating a false picture of liquidity.
3.  **Hidden Burn:** Traditional P&L reporting hides the inefficiency of specific teams ("Squads") that rely heavily on expensive freelancers.

---

## 🏗 The Solution Architecture

I designed an automated pipeline that ingests raw data, applies accounting logic, and outputs decision-ready dashboards.

```mermaid
graph TD
    A[Data Sources] -->|Export| B(Processing Engine - Python)
    
    subgraph Sources
    A1[Facebook/Google Ads API]
    A2[Xero - Client Fund Ledger]
    A3[Deel/Payroll Data]
    end
    
    B -->|Reconcile| C{"Ad Spend<br/>Match?"}
    C -->|Yes| D["Clear Liability<br/>(No Risk)"]
    C -->|No| E["Flag Variance<br/>Report"]
    
    B -->|Allocate| F[Squad P&L Model]
    
    F -->|Output| G[Executive Dashboard]
    G --> H["Profitability<br/>per Squad"]
    G --> I["Cash Flow<br/>Float Risk"]
