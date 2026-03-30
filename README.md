<div align="center">

# 🛒 Street Vendors Analysis — Mumbai

### A Statistical & Machine Learning Study of Urban Informal Economy

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-Statistical%20Modeling-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-Data%20Handling-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge&logo=python&logoColor=white)

<br>

> *"Unlike traditional qualitative studies, this project uses statistical modeling and machine learning to generate actionable, data-driven insights into Mumbai's informal street economy."*

<br>

![Status](https://img.shields.io/badge/Status-Completed-2ecc71?style=flat-square)
![Survey](https://img.shields.io/badge/Survey%20Size-400%20Vendors-e74c3c?style=flat-square)
![Models](https://img.shields.io/badge/Models-3%20Built-9b59b6?style=flat-square)
![City](https://img.shields.io/badge/City-Mumbai%2C%20India-f39c12?style=flat-square)

</div>

---

## 📌 Project Overview

Street vending is the backbone of Mumbai's urban informal economy — yet it remains largely unstudied through a data science lens. This project bridges that gap by applying **statistical modeling, machine learning clustering, and regression analysis** to primary survey data collected from **400 street vendors** across Mumbai's railway lines.

The study answers three core questions:

```
┌─────────────────────────────────────────────────────────────┐
│  1. 💰 What socio-economic factors determine vendor income? │
│  2. 🌍 Are migration patterns random or structured?         │
│  3. 👥 What drives daily customer footfall?                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎯 Objectives

| # | Objective | Method Used |
|---|-----------|-------------|
| 1 | Analyze impact of socio-economic factors on vendor income | Multiple Linear Regression (R) |
| 2 | Identify and segment migration patterns | K-Modes Clustering (Python) |
| 3 | Model daily customer count | Poisson Regression (R) |
| 4 | Validate statistical assumptions | Box-Cox, Normality & Homoscedasticity Tests |

---

## 🗂️ Dataset

### Survey Design

```
mermaid
flowchart TD
    A["🗺️ Mumbai Street Vendors Survey
    ────────────────────────────
    400 Vendors · Stratified Sampling"]

    A --> B["🔵 Western Line
    ─────────────────
    High Footfall Zone
    ~120 vendors · 30%"]

    A --> C["🟢 Central Line
    ─────────────────
    Mixed Income Zone
    ~100 vendors · 25%"]

    A --> D["🟡 Harbour Line
    ─────────────────
    Lower Income Zone
    ~100 vendors · 25%"]

    A --> E["🟣 Trans Harbour Line
    ─────────────────────
    Peripheral Zone
    ~80 vendors · 20%"]

    B --> F["📊 Combined Dataset
    ───────────────────────────────
    400 Vendors · 53 Features
    Demographics · Income · Migration · Footfall"]

    C --> F
    D --> F
    E --> F

    style A fill:#F1EFE8,stroke:#5F5E5A,color:#2C2C2A
    style B fill:#E6F1FB,stroke:#185FA5,color:#0C447C
    style C fill:#E1F5EE,stroke:#0F6E56,color:#085041
    style D fill:#FAEEDA,stroke:#854F0B,color:#633806
    style E fill:#EEEDFE,stroke:#534AB7,color:#3C3489
    style F fill:#FAECE7,stroke:#993C1D,color:#712B13
```

> **Sampling Method:** Stratified random sampling across 4 railway lines to ensure geographic representation

### Feature Categories

| Category | Features |
|----------|---------|
| 👤 Demographics | Age, Gender, Education Level, Family Size |
| 🏪 Business | Product Type, Working Hours, Stall Type |
| 🚚 Migration | Origin State, Years in Mumbai, Migration Reason |
| 💰 Economic | Monthly Income, Daily Customer Count, Expenses |

---

## ⚙️ Methodology Pipeline

```
Raw Survey Data (400 vendors)
         │
         ▼
┌─────────────────────┐
│  Data Cleaning &    │  ← Handle missing values, outliers,
│  Preprocessing      │    encode categorical variables
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Exploratory Data   │  ← Distribution analysis,
│  Analysis (EDA)     │    correlation heatmaps, visualizations
└──────────┬──────────┘
           │
     ┌─────┴──────┐
     │            │
     ▼            ▼
┌─────────┐  ┌──────────┐
│Multiple │  │ K-Modes  │
│Linear   │  │Clustering│
│Regression│  │(Python) │
│  (R)    │  └────┬─────┘
└────┬────┘       │
     │            ▼
     │     ┌──────────────┐
     │     │  3 Vendor    │
     │     │  Segments    │
     │     └──────────────┘
     ▼
┌─────────────────────┐
│  Poisson Regression │  ← Count-based model for
│       (R)           │    daily customer footfall
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Policy Insights &  │
│  Recommendations    │
└─────────────────────┘
```

---

## 📊 Analysis & Results

### 🔹 1. Exploratory Data Analysis

**Key patterns discovered:**
- Income distribution is right-skewed — majority earn below ₹15,000/month
- Western Line vendors earn 23% more on average than Harbour Line vendors
- Food vendors outnumber non-food vendors 3:1 but income gap is significant
- Peak working hours: 8AM–10AM and 5PM–9PM (aligned with commuter rush)

---

### 🔹 2. Multiple Linear Regression — Income Prediction

**Target variable:** Monthly Income (₹)

**Model Performance:**

```
┌────────────────────────────────────────┐
│  Adjusted R²  =  0.43   (Moderate Fit) │
│  p-value      <  0.05   (Significant)  │
│  F-statistic  =  Significant           │
└────────────────────────────────────────┘
```

**Statistical Assumptions Validated:**

| Test | Method | Result |
|------|--------|--------|
| Normality of residuals | Shapiro-Wilk + Q-Q Plot | ✅ Passed after Box-Cox |
| Homoscedasticity | Breusch-Pagan Test | ✅ Passed |
| Multicollinearity | VIF Score | ✅ All VIF < 5 |
| Linearity | Residual vs Fitted Plot | ✅ Passed |

**Key Findings:**

| Factor | Effect on Income | Significance |
|--------|-----------------|--------------|
| 📍 Western Region | ↑ Significantly higher income | p < 0.01 |
| 🍎 Food Vendors | ↑ Higher income vs non-food | p < 0.01 |
| ⏰ Working Hours | ↑ More hours = more income | p < 0.05 |
| 🎓 Education Level | Marginal positive effect | p < 0.05 |
| 👤 Gender (Female) | ↓ Lower income on average | p < 0.05 |

---

### 🔹 3. K-Modes Clustering — Migration Segmentation

> K-Modes was chosen over K-Means because all features are **categorical** — a key methodological decision that shows statistical rigor.

**3 Vendor Segments Identified:**

```
┌────────────────────────────────────────────────────────────┐
│                                                            │
│  Segment 1 — 🧳 Economic Migrants                          │
│  ─────────────────────────────────                         │
│  • Migrated from low-income states (UP, Bihar, Rajasthan)  │
│  • Low income, high family dependency                      │
│  • Mostly non-food vendors in peripheral zones             │
│                                                            │
│  Segment 2 — 🏠 Stable Locals                              │
│  ────────────────────────────                              │
│  • Mumbai natives or long-term residents (10+ years)       │
│  • Steady income, established customer base                │
│  • Higher proportion of food vendors in prime locations    │
│                                                            │
│  Segment 3 — 🚀 Opportunity Seekers                        │
│  ──────────────────────────────────                        │
│  • Recent migrants targeting high-footfall markets         │
│  • Mid-range income, high ambition indicators              │
│  • Western and Central Line concentration                  │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

> **Key Insight:** Migration is **structured, not random** — vendors migrate to specific zones based on prior social networks and product-market fit.

---

### 🔹 4. Poisson Regression — Customer Footfall Model

**Target variable:** Daily Customer Count

> Poisson regression was chosen because customer count is a **discrete count variable** — using linear regression here would be statistically incorrect.

**Key Findings:**

| Factor | Effect on Customer Count | Direction |
|--------|-------------------------|-----------|
| ⏰ Full-day vending (8+ hrs) | +34% more customers | ↑ |
| 🍎 Food product type | +28% more customers | ↑ |
| 📍 Western Line location | +19% more customers | ↑ |
| 🎓 Higher education | Marginal positive | ↑ |
| 🌙 Evening-only vending | −22% fewer customers | ↓ |

---

## 📈 Key Insights Summary

```
╔══════════════════════════════════════════════════════════════╗
║                    HEADLINE FINDINGS                         ║
╠══════════════════════════════════════════════════════════════╣
║  💡 Region & product type are the strongest income drivers   ║
║  💡 Non-food vendors earn 35–40% less than food vendors      ║
║  💡 Migration follows structured social network patterns     ║
║  💡 Working hours directly and significantly impact footfall ║
║  💡 Western Line vendors are highest earning segment         ║
║  💡 Female vendors face consistent income gap of ~18%        ║
╚══════════════════════════════════════════════════════════════╝
```

---

## 🛠️ Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| 🐍 Python | 3.x | K-Modes clustering, preprocessing |
| 🟢 R | 4.x | Linear & Poisson regression, assumption tests |
| 📊 Excel | — | Raw data entry, initial cleaning |
| 📉 Matplotlib | Latest | Distribution & trend plots |
| 🎨 Seaborn | Latest | Correlation heatmaps, boxplots |
| 📦 kmodes | Python lib | Categorical clustering |

---

## 💡 Policy & Business Recommendations

| # | Recommendation | Target Group |
|---|----------------|-------------|
| 1 | 📢 Marketing & digital literacy training for non-food vendors | Non-food vendors |
| 2 | 🏗️ Infrastructure upgrades in Harbour & Trans-Harbour zones | Low-income regions |
| 3 | ⏰ Incentivize full-day vending through licensing benefits | Part-time vendors |
| 4 | 🎯 Targeted urban livelihood schemes for Economic Migrants | Segment 1 vendors |
| 5 | 👩 Gender-focused support programs to close income gap | Female vendors |
| 6 | 🗺️ Zoning policy based on cluster segment needs | Municipal Corp. |

---

## 📁 Project Structure

blackbook (1).docx
```
street-vendors-mumbai/
│
├── 📂 data/
│   ├── raw_survey_data.xlsx          ← Primary survey (400 vendors)
│   └── cleaned_data.csv              ← Preprocessed dataset
│
├── 📂 notebooks/
│   ├── 01_EDA.ipynb                  ← Exploratory analysis
│   └── 02_clustering.ipynb           ← K-Modes segmentation
│
├── 📂 r_scripts/
│   ├── linear_regression.R           ← Income model
│   └── poisson_regression.R          ← Footfall model
│
├── 📂 visualizations/
│   └── plots/                        ← All charts and figures
│
└── README.md
```

---

## 🔮 Future Scope

- [ ] Collect longitudinal data (track same vendors over 2–3 years)
- [ ] Add geospatial mapping of vendor locations using Folium
- [ ] Build a Streamlit dashboard for interactive exploration
- [ ] Apply NLP on vendor feedback for sentiment analysis
- [ ] Expand study to other Indian metros (Delhi, Bangalore)

---

## 👩‍💻 About the Author

<div align="center">

**Ekta Shirsulla**

M.Sc. Statistics | Data Analyst | Aspiring Data Scientist

Mumbai, Maharashtra, India

📧 ektashirsulla26@gmail.com &nbsp;|&nbsp;
🔗 [LinkedIn](https://www.linkedin.com/in/ekta-shirsulla) &nbsp;|&nbsp;
🐙 [GitHub](https://github.com/ektashirsulla26-source)

*If you found this project useful, give it a ⭐ on GitHub and feel free to connect!*

</div>

---

<div align="center">

*Built with ❤️ using Python, R, and a passion for turning data into decisions*

</div>

     
