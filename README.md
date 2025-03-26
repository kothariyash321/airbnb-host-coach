
# 🏡 Airbnb Host Coach: From Host to Superhost with AI

![Airbnb Logo](https://cdn.freebiesupply.com/logos/large/2x/airbnb-2-logo-png-transparent.png) <!-- (or replace with a project-relevant visual) -->

> **Empowering Airbnb Hosts with AI-Powered Coaching to Achieve Superhost Status and Maximize Revenue**

---

## 📌 Project Overview

This project presents a scalable, AI-driven solution that enables **Airbnb hosts** to:
- Improve their performance and become **Superhosts**
- Maximize **revenue** through dynamic pricing strategies
- Identify **high-growth neighborhoods** for expansion via clustering and predictive modeling

Our system leverages **Gradient Boosted Decision Trees**, **KMeans Clustering**, and a custom-built **Growth Potential Index (GPI)** to deliver personalized, data-driven recommendations to hosts.

---

## 🧠 Problem Statement

Airbnb currently faces:
- Hosts lacking actionable insights to improve their status and revenue
- Inadequate tools for spotting high-growth neighborhoods
- Market imbalances in supply and demand across regions

These issues lead to **revenue loss**, **guest dissatisfaction**, and **competitive threats** from platforms like Vrbo and Booking.com.

---

## 🎯 Solution: Airbnb Host Coach

A **GenAI-powered system** providing personalized host coaching and predictive insights to:
- Boost occupancy rates
- Reduce cancellations
- Enhance guest experience
- Encourage investment in high-GPI neighborhoods

---

## 🔍 Exploratory Data Analysis (EDA)

Key insights from the dataset:

- **Superhosts vs Non-Superhosts**
  - Higher occupancy rates ✅
  - Ability to command premium prices 💰
  - Found more frequently in neighborhoods like Lakeview and Near North Side

**📊 EDA Visuals:**
> ✅ _Insert charts from notebook for Occupancy vs Price, Cancellations vs Revenue, Guest Count vs Rate_

---

## 🛠️ Data Preprocessing

| Task                  | Approach |
|-----------------------|----------|
| Missing Values        | Imputation (mean/median/mode or 'Unknown') |
| Outlier Treatment     | Winsorization using 5th–95th percentiles |
| Collinearity Check    | VIF threshold > 0.95, removed variables |
| Feature Selection     | Gradient Boosting + Mutual Information |
| Encoding              | Target Encoding + One-Hot Encoding |
| Class Imbalance       | SMOTE Oversampling |

---

## 🔮 Predictive Modeling

### 🎯 Gradient Boosted Decision Tree (GBDT)

- **Goal**: Predict probability of a host becoming a **Superhost**
- **AUC-ROC**: 0.9857 ✅
- **Top Predictors**: Past cancellations, overall rating, prior Superhost status

```python
# Sample model evaluation
print("AUC Score:", roc_auc_score(y_test, model.predict_proba(X_test)[:,1]))
```

---

## 🧭 Clustering with KMeans

Used to segment properties by growth potential using:
- Booking-to-revenue ratio
- Occupancy rate
- Superhost density

🔍 **Clusters**: High-Growth, Moderate-Growth, Low-Growth  
✅ Optimal clusters determined using the Elbow Method.

---

## 🌱 Growth Potential Index (GPI)

A unified metric (range: 0.0 to 1.0) combining:
- Superhost probability
- Cluster insights
- Host performance metrics

```python
GPI = (0.25 * superhost_prob +
       0.20 * occupancy_rate +
       0.20 * cluster_score +
       0.15 * rating_score +
       0.10 * cancellation_penalty +
       0.10 * revenue_per_booking)
```

📈 _GPI enables personalized insights:_
- High-GPI Hosts → Expansion or price optimization
- Low-GPI Hosts → Targeted recommendations to improve service

---

## 📈 Key Results

| Metric                 | Result     |
|------------------------|------------|
| Superhost Prediction   | 94% Precision & Recall |
| GPI                    | 0.0 – 1.0 Scale |
| Model AUC              | 0.9857 |
| Personalized Insights  | Yes ✅ |

---

## 💡 Real-World Impact

### For Hosts:
- Become a Superhost faster
- Improve guest reviews and revenue
- Enter high-growth areas

### For Airbnb:
- Increased platform loyalty
- Market-level growth in untapped areas

### For Guests:
- Better experiences from high-quality hosts
- Affordable dynamic pricing options

---

## 📊 Sample Visualizations

| Visualization | Description |
|---------------|-------------|
| ![EDA1](images/occupancy_vs_price.png) | Occupancy Rate vs Booking Price |
| ![EDA2](images/cancellations_vs_revenue.png) | Cancellation Impact on Revenue |
| ![GPI](images/gpi_clusters.png) | Growth Potential Index by Cluster |


---

## 🚀 Future Scope

- Integrate **GenAI** for real-time host coaching (recommendations, prompts)
- Develop a **dashboard** for GPI and Superhost tracking
- Deploy as a **SaaS product** for Airbnb and similar platforms

---

## 👨‍💻 Contributors

- **Harshal Amin**  
- **Yash Kothari**

---

## 📚 References

- [How I Became a Superhost](https://simplyvinita.medium.com/how-i-built-a-profitable-airbnb-business-from-new-host-to-superhost-a4bb3594d3f2)
- [Airbnb + AI Integration](https://techcrunch.com/2024/02/13/airbnb-plans-to-use-ai-including-its-gameplanner-acquisition-to-create-the-ultimate-concierge/)
- [GenAI Prompt Example](https://chatgpt.com/c/674102a9-ecf8-800b-be34-fca212b67838)

---
