# Midas Nowcasting | Food Inflation Dashboard

Interactive Quarto Dashboard presenting real-time food inflation nowcasts, weekly revision pathways, contribution decompositions, and seasonal patterns across all 27 European Union Member States.

Live Interactive Dashboard: **[https://jakubrybacki.github.io/midas-food-inflation-dashboard/](https://jakubrybacki.github.io/midas-food-inflation-dashboard/)**

---

## 📈 Methodology Overview

The dashboard combines two econometric model classes:
1. **Unrestricted Mixed-Data Sampling (U-MIDAS)**:
   - For volatile agricultural categories (*Bread & Cereals, Meat, Milk/Cheese/Eggs, Oils & Fats, Fruits, Vegetables*).
   - Driven by high-frequency weekly commodity spot prices from the European Commission Directorate-General for Agriculture and Rural Development (**DG AGRI**).
2. **Seasonal Autoregressive with Dummies (SAR-D)**:
   - For structural categories (*Fish & Seafood, Sugar & Sweets, Food Products n.e.c.*).
   - Driven by historical seasonal cycles and Eurostat HICP inertia.

All category nowcasts are aggregated bottom-up using official **Eurostat ECOICOP-2 consumption weights (CP011)** to produce the Total Food basket nowcast (both m/m and y/y).

---

## 🚀 Key Modules

1. **🎯 Nowcasts & Decomposition**:
   - Primary KPI valueboxes for Total Food and all 9 COICOP sectors (CP0111 to CP0119) with both month-on-month (**m/m**) and year-on-year (**y/y**) rates.
   - Interactive Plotly waterfall decompositions (trend, autoregressive inertia, DG AGRI commodity shocks).
   - Horizontal top drivers bar charts.
   - Cross-country EU-27 benchmark rankings with active country highlighting.

2. **📅 Seasonal Pattern vs Nowcast**:
   - Historical multi-year seasonal benchmarks (2015–2025) vs current nowcast to evaluate whether projections align with historical trends.
   - Seasonal deviation metrics and outlier flags.

3. **🔄 Within-Month Revisions ($W1 ightarrow W4$)**:
   - Tracking weekly forecast convergence from initial week ($W1$) to final estimate ($W4$).
   - Multi-month forecast stability indicators and verification against published Eurostat HICP figures.

4. **🌍 EU-27 Cross-Country Database**:
   - Comprehensive interactive data table covering all 27 Member States with search, filtering, and export capabilities.

---

## 💻 Tech Stack

- **Quarto Dashboards (v1.4+)**
- **Python 3.12** (`plotly`, `itables`, `pandas`, `numpy`)
- **Data Backend**: Google Cloud BigQuery & Eurostat API
- **Deployment**: GitHub Pages
