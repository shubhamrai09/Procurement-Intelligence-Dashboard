# 📦 Procurement Intelligence Dashboard

**Searchable, vendor-and-material-level procurement intelligence — built from raw Tally ERP purchase records. No backend. No database. One HTML file.**

![HTML5](https://img.shields.io/badge/HTML5-Structure-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-Styling-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-Visualization-FF6384?style=flat-square&logo=chartdotjs&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2EA44F?style=flat-square)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Screenshots](#️-screenshots)
- [About the Dataset](#️-about-the-dataset)
- [Project Workflow](#-project-workflow)
- [Key Features](#-key-features)
- [Business Problem](#-business-problem)
- [Project Objectives](#-project-objectives)
- [Tools & Technologies](#️-tools--technologies)
- [How to Use](#-how-to-use)
- [Business Impact](#-business-impact)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 🧭 Overview

Procurement teams don't struggle because they lack data — they struggle because their data lives in an ERP export, and the questions they actually need answered ("who do we buy this from, at what price, how often") live somewhere else entirely.

This dashboard takes raw purchase-voucher data exported from **Tally ERP** and turns it into an interactive, single-file web application where any material, vendor, or transaction can be found, cross-referenced, and visualized in seconds — no setup beyond opening a file in a browser.

The underlying dataset is real purchase history from **Goyal Petrofils Yarns Pvt. Ltd.** (Ludhiana, Punjab) — purchase vouchers (`PURCHASE STORE` / `GENERAL PURCHASE STORE`) dated from 1‑Apr‑2019 onward — a genuine operational case study, not a synthetic demo.

---

## 🖼️ Screenshots

> No screenshots are included yet. Once captured, add them under `assets/screenshots/` and reference them here:
>
> ```markdown
> ![Overview page](assets/screenshots/overview.png)
> ![Vendor profile](assets/screenshots/vendor-profile.png)
> ![Transaction explorer](assets/screenshots/transactions.png)
> ```

---

## 🗂️ About the Dataset

- **Source:** Tally ERP purchase-voucher export (voucher types `PURCHASE STORE` and `GENERAL PURCHASE STORE`)
- **Coverage:** 1‑Apr‑2019 through the latest available transaction date
- **Granularity:** individual purchase transactions, each carrying vendor, material, item group, quantity, rate, amount, date, voucher type, and PO number
- **Categorization:** item groups are mapped from the Tally stock-item master; materials not found in that master are grouped under "Uncategorized"
- **Data integrity:** fields missing from the source export are explicitly shown as **"Data Not Available"** rather than estimated or filled in

---

## 🔁 Project Workflow

1. Purchase vouchers are exported from Tally ERP.
2. The export is embedded directly into the page and parsed in-browser into normalized lookups — vendors, materials, item groups, financial years.
3. Transactions are aggregated on load into vendor-level, material-level, and item-group-level summaries.
4. Each view (Overview, Vendor, Material, Transactions, Opportunities, …) renders straight from those in-browser aggregates — no server round-trip, no API call.

---

## ✨ Key Features

- 🔍 **Global smart search** across every vendor and material, with live suggestions
- 🏭 **Vendor intelligence** — searchable directory; full catalogue, purchase history, and active/inactive/new status per vendor
- 🧵 **Material intelligence** — per-material profile showing every vendor that supplies it
- 🗂️ **Item group drill-down** for category-level analysis
- 📅 **Year-wise trend analysis** with automatic financial-year detection
- 💰 **Price analysis** per material, across vendors and time
- ⚖️ **Procurement opportunities view** — single-source materials (dependency risk) and multi-vendor price variance (potential savings)
- 📋 **Transaction explorer** — filter by FY, voucher type, or free text; sortable, paginated, exportable to CSV
- 📊 **Data visualization** via Chart.js throughout
- ⚡ **Zero setup** — one self-contained HTML file, dataset included

---

## 🧩 Business Problem

ERP systems like Tally are built for bookkeeping, not analysis. Answering everyday procurement questions — *which vendors supply this material, is this vendor still active, where are we paying different prices for the same item* — means manually filtering exports and rebuilding the same cross-reference every time. That doesn't scale, and it buries exactly the insights (vendor concentration, pricing gaps, dormant suppliers) that matter most.

---

## 🎯 Project Objectives

- Make **material discovery** instant
- Make **vendor visibility** immediate
- Surface **procurement risk and opportunity** proactively, not on request
- Replace static spreadsheet exports with an always-navigable, filterable view

---

## 🛠️ Tools & Technologies

| Category | Technology |
|---|---|
| Structure | HTML5 |
| Styling | CSS3 (custom properties, no framework) |
| Logic | Vanilla JavaScript (ES6+) |
| Charts | [Chart.js 4.4.0](https://www.chartjs.org/) (CDN) |
| Typography | Google Fonts — IBM Plex Sans / IBM Plex Mono |
| Architecture | Single static HTML file — no backend, no database, no build step |

---

## 🚀 How to Use

1. Download or clone the repository.
2. Open the HTML file directly in any modern browser:
```bash
   open procurement_dashboard.html        # macOS
   start procurement_dashboard.html       # Windows
   xdg-open procurement_dashboard.html    # Linux
```
3. Navigate via the sidebar — Overview, Vendors, Materials, Item Groups, Year-wise, Status, Price Analysis, Opportunities, Transactions.
4. Use the top search bar to jump directly to any vendor or material.
5. On the Transactions page, filter by FY / voucher type / free text, then **Export** to CSV.

---


## 📈 Business Impact

- **Faster vendor and material lookup** — replaces manual spreadsheet filtering with instant search.
- **Clearer supplier visibility** — active, inactive, and newly onboarded vendors are visible at a glance, every financial year.
- **Earlier warning on sourcing risk** — single-source materials are surfaced automatically, instead of being discovered only after a supplier fails to deliver.
- **Stronger footing in vendor negotiations** — seeing exactly how much two vendors charge for the same material, side by side, turns a price conversation from guesswork into a documented ask.
- **Less dependency on institutional memory** — "who do we buy this from" no longer lives only in one person's head; anyone can look it up.
- **Faster onboarding for new procurement staff** — new team members can explore vendor and material history themselves instead of being walked through raw ERP exports.
- **Quicker management and audit review** — purchase history by vendor, material, or financial year is already organized, instead of being reconstructed by hand for every review.
- **Supports smarter vendor consolidation decisions** — multi-vendor materials with wide price variance are flagged for review rather than left to be noticed by chance.
- **Reusable, not one-off** — once built, refreshing the dashboard with a new Tally export is a data swap, not a rebuild.

*(No specific time-saved or cost-saved figures are claimed — these haven't been formally measured.)*

---

## 🔮 Future Enhancements

- 🔄 Automated data refresh from new Tally exports
- 🤝 Advanced supplier scorecards beyond pairwise price variance
- 🔮 Predictive procurement analytics (demand/price forecasting)
- 🗄️ Backend + database layer for larger datasets and multi-user access
- 🔐 Role-based access control
- 📱 Responsive/mobile layout

---

## 👤 Author

**Shubham Rai**

---

<div align="center">
<sub>Built to turn raw ERP purchase data into procurement decisions — not just reports.</sub>
</div>
