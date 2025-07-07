# 📊 Causal Machine Learning for Evaluating the Impact of Renewable Energy Policies in India

## 🌍 Project Objective

The goal of this project is to **evaluate the effectiveness of renewable energy policies** implemented in selected Indian states using **causal inference techniques**. Specifically, we estimate:

✅ Whether these policies led to an increase in renewable energy capacity  
✅ How different states responded to these policies  

---

## 📂 Dataset Description

We utilize the **India Yearly Electricity Dataset** from **[Ember](https://ember-climate.org/)**, which provides annual, state-wise data on electricity generation and capacity by source.

- **Timeframe**: Multiple years up to **2022**  
- **Features Used**:
  - `Capacity_Renewables`, `Capacity_Fossil`, `Capacity_Clean`, `Capacity_Other`
  - `State`
  - `Year`  
- **Target Variable (Y)**: `Capacity_Renewables`  
- **Treatment Variable (T)**: Binary indicator for whether a state was targeted by renewable policies  

---

## 🏷️ Treatment Definition

We adopted a **state-based treatment** definition to reflect real-world policy targeting, rather than a simple time-based cutoff. Certain Indian states known for leading renewable transitions were marked as treated.

---

## ⚙️ Methods Used

We applied three approaches to estimate the **causal treatment effect**:

| Method              | Description                                                                 |
|---------------------|----------------------------------------------------------------------------|
| **OLS**             | Baseline linear regression assuming constant effect across states           |
| **DML**             | Double Machine Learning: Uses ML to control confounders and estimate effect |
| **Causal Forest**   | CausalForestDML: Estimates heterogeneous treatment effects across states    |

---

## 📈 Results Summary

| Method           | Estimated Effect (MW) | Notes                                               |
|------------------|----------------------|-----------------------------------------------------|
| **OLS**          | 0.68                 | Naive average effect                                |
| **DML**          | 687.59               | Stronger signal after adjusting for confounders     |
| **Causal Forest**| Varies per state (avg ≈ 687) | Reveals heterogeneity across states |

**Key Insights**:

✅ **DML** shows a significant positive impact after accounting for covariates  
✅ **Causal Forest** produces similar average effects to DML but uncovers how impacts vary state by state  
✅ On average, renewable policies led to ~**687 MW** (or **0.687 GW**) more renewable capacity in treated states compared to similar untreated states  

---

## 🚀 Why Causal Machine Learning Performs Better

| Issue with Traditional Methods       | How Causal ML Solves It                                |
|--------------------------------------|-------------------------------------------------------|
| Assumes linearity and no hidden bias | DML learns flexible, non-linear functions to reduce bias |
| Only estimates a single average effect | Causal Forest provides **CATEs** (Conditional Average Treatment Effects) revealing state-specific variations |

---

## ✅ Conclusion

This study demonstrates that **Causal Machine Learning techniques**, such as **DML** and **Causal Forests**, offer more accurate and interpretable evaluations of energy policies compared to traditional econometric models. Our analysis confirms that renewable energy policies implemented in selected Indian states have significantly boosted renewable capacity.

---

## 📎 Attachments & Resources

- **Jupyter Notebook**: [Link to Notebook](https://colab.research.google.com/drive/1FAtBxB-hA_8fkxKAy854XPtYot7LwMlE?usp=drive_link)  
- **Dataset Source**: [Ember's India Yearly Electricity Dataset](https://ember-climate.org/)

---

*For questions or collaboration, feel free to connect!* 🚀
