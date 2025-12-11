<div align="center">

# 🛡️ Revenue Assurance & Billing Control
### Automating the Link Between Operations (Project Log) and Finance (Xero)

![Python](https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge&logo=python&logoColor=white)
![Xero](https://img.shields.io/badge/Xero-Revenue%20Check-13b5ea?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Cleaning-150458?style=for-the-badge&logo=pandas)

</div>

---

## 💼 Executive Summary

**The Risk:** In high-growth agencies, "Work Done" does not always equal "Invoice Sent." Disconnects between Project Management tools (Monday.com/Salesforce) and Finance tools (Xero) lead to **Revenue Leakage**.

**The Solution:** This module performs an automated **Revenue Assurance** audit. It aggregates raw Xero sales data and reconciles it against the Master Project Log to ensure every completed milestone has been billed correctly.

---

## 🔻 The Business Problem

1.  **Fragmentation:** Project Managers track completion in one system; Finance tracks invoices in Xero.
2.  **Messy Data:** A single project fee (e.g., £2,000) might be split across 3 lines in a Xero invoice, making manual matching impossible.
3.  **Silent Loss:** If an invoice is *never raised*, Xero won't tell you. You need an external control to catch the missing revenue.

---

## 🏗 The Automation Logic

I designed a script that acts as a bridge between **Operations** and **Finance**.

```mermaid
graph TD
    A[Master Project Log] -->|Input| C(Python Aggregator)
    B[Xero Sales Export] -->|Input| C
    
    C -->|Step 1: Clean| D[Group Xero Lines by Ref]
    D -->|Step 2: Match| E{Compare Totals}
    
    E -->|Match| F[✅ Billed Correctly]
    E -->|Variance| G[⚠️ Under/Over Charged]
    E -->|Missing| H[🚨 REVENUE LEAK DETECTED]
