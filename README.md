# ⭐ What Drives Negative Reviews on Olist?

Exploratory data analysis and predictive modeling to understand what factors drive negative reviews (1–2 stars) on Olist, a Brazilian e-commerce platform.

---

## 📋 Overview

Around **13% of delivered orders on Olist receive a negative review**. This project investigates whether the root cause is logistics, product quality, or both — with the goal of producing actionable recommendations.

**Central question:** What factors predict a negative review?

---

## 🔍 Analysis Structure

1. **Review score distribution** — scale and profile of the problem
2. **Delivery time hypothesis** — do longer deliveries drive negative reviews?
3. **Missing the promised date** — does failing to meet the estimated delivery date matter more than absolute delay?
4. **Geographic breakdown** — do some states have systematically worse reviews?
5. **Category breakdown** — are some products generating complaints regardless of delivery speed?
6. **Predictive model** — which factors independently predict a negative review?
7. **Conclusions & recommendations**

---

## 📊 Key Findings

- **Missing the promised date is the strongest predictor.** On-time orders have a 9.2% negative rate. Orders 4–7 days late jump to 61%. Orders 8+ days late reach ~79%.
- **Expectation management matters as much as actual speed.** Even 1–3 days past the promised date pushes the negative rate from 9% to 19% — before delivery is unusually slow in absolute terms.
- **Rio de Janeiro is an outlier.** RJ has 18.3% negative reviews despite an average of only 15.2 delivery days, suggesting a region-specific problem beyond raw delivery time.
- **Some categories have product quality issues.** Fixed telephony, audio, and furniture show above-average negative rates *despite fast delivery*, pointing to product-level problems rather than logistics.
- **The Random Forest model achieves CV F1 ≈ 0.48**, well above a naïve baseline — and confirms that days past the promised date and raw delivery time are the top predictive features.

---

## 🛠️ Tech Stack

- **Python** — pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn
- **SQL** — SQLite (in-memory) for data extraction and aggregation
- **Dataset** — [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle)

---

## 📌 Recommendations

| Priority | Action | Rationale |
|----------|--------|-----------|
| 🔴 High | Improve delivery date estimation accuracy | Biggest single driver of negative reviews |
| 🔴 High | Investigate RJ logistics specifically | High negative rate not explained by delivery time |
| 🟡 Medium | Audit product quality in flagged categories | Fixed telephony, audio, furniture have product-level issues |
| 🟡 Medium | Improve logistics for northern/northeastern states | Structural delivery time problem |

---

## ⚠️ Limitations

- Review text was not analyzed — delivery and product complaints within a single review cannot be separated.
- The model captures correlation, not causation.
- Customers who don't leave reviews are excluded — their satisfaction level is unknown.
- Data covers 2016–2018; logistics infrastructure may have changed since then.

---

*Analysis by [your name] — combining SQL-based data extraction with Python modeling on a real e-commerce dataset.*
