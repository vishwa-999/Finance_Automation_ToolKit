<div align="center">

# 🛡️ Media Spend Reconciliation Engine
### Automated Financial Control for High-Volume Ad Spend

![Python](https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Cleaning-150458?style=for-the-badge&logo=pandas)
![Xero](https://img.shields.io/badge/Xero-API%20Integration-13b5ea?style=for-the-badge)
![Finance](https://img.shields.io/badge/Finance-Audit%20%26%20Control-green?style=for-the-badge)

</div>

---

## 💼 Executive Summary

**The Business Risk:** Marketing agencies often act as a "bank" for client ad spend. If a £5,000 charge from Facebook is paid via credit card but **missing** from the accounting ledger (Xero), the company's liability is understated and profit is overstated.

**The Solution:** This Python engine automates the reconciliation of **"The Truth"** (Platform Export) against **"The Ledger"** (Xero Export). It handles messy real-world data issues—such as non-standard headers and currency formatting—to identify cash risks in seconds.

---

## 🔻 The Data Problem

Financial data is rarely clean. In this specific project, I solved three common data engineering challenges found in Xero exports:

1.  **Offset Headers:** Xero reports often include 4-5 lines of title text before the actual column headers, breaking standard import scripts.
2.  **Dirty Strings:** Currency fields often contain symbols (`£`, `$`) and whitespace that prevent mathematical comparison.
3.  **Missing Keys:** Transactions often exist in the ad platform but are completely absent from the accounting ledger due to human error.

---

## 🏗 The Automation Architecture

```mermaid
graph TD
    A[Facebook/Google Ads Export] -->|Input| C(Python Cleaning Engine)
    B[Xero Purchases Export] -->|Input| C
    
    subgraph "Step 2: Data Engineering"
    C -->|Clean| D[Skip Top 4 Rows header=4]
    D -->|Format| E[Regex Clean: Remove £ symbols]
    end
    
    E -->|Step 3: Match| F{Transaction ID Match?}
    
    F -->|Match| G[✅ RECONCILED]
    F -->|Variance| H[⚠️ PRICE VARIANCE]
    F -->|Missing| I[🚨 CRITICAL: MISSING INVOICE]



