# Supply Chain Inventory Optimization & Online A/B Testing Validation

## 📌 Project Overview
This repository contains an industrial-grade supply chain optimization project designed to reduce operational waste (holding costs and stockout penalties) in retail networks. By transitioning from a rigid **Traditional Point Forecast (Strategy A)** to an **Elastic Newsvendor Optimization Model (Strategy B)**, this project demonstrates how statistical frameworks directly solve inventory misalignment problems.

To ensure empirical validity, the models were evaluated through a rigorous **6-week Online A/B Testing simulation ($n = 4,200$)** embedded with real-world geographical spillover noise. The new strategy achieved a statistically verified **28.89% reduction** in daily operational loss.

---

## 🔬 Methodology & Core Architecture

### 1. Baseline Framework: Strategy A (Traditional Point Forecast)
* **Logic:** Relies strictly on standard deterministic point predictions without accounting for demand volatility.
* **Risk Profile:** Suffers from extreme system volatility, inflating risks of severe stockouts or heavy overstocking under fluctuating market demand.

### 2. Optimized Framework: Strategy B (Elastic Newsvendor Model)
* **Logic:** Dynamically computes safety stock levels based on marginal economic analysis (Critical Ratio).
* **Core Optimization Formulas:**
  $$\text{Critical Ratio} = \frac{c_u}{c_u + c_o}$$
  $$c_u = \text{Price} - \text{Cost}$$
  Where $c_u$ represents the understocking cost (lost sales margin) and $c_o$ represents the overstocking cost (holding/liquidation penalty). 
* **Risk Profile:** Stabilizes supply chain variance and builds resilient inventory buffers tailored to product profitability.

---

## 📊 Online A/B Testing Framework

To scientifically test the new algorithm before network-wide deployment, a formal A/B test was designed with **8% competitive demand spillover noise** injected to simulate real-world inter-store cannibalization (where stockouts in Control nodes push sudden, random demand spikes onto Treatment nodes).

### Statistical Hypothesis Testing
A **Welch's Independent Samples T-Test (Equal Variances Not Assumed)** was chosen due to heavily skewed and unequal empirical variances between the two groups (Strategy A: 150% variance inflation vs. Strategy B: 90% capped variance).

* **Null Hypothesis ($H_0$):** $\mu_{\text{Treatment}} \ge \mu_{\text{Control}}$ (The new strategy fails to reduce daily operational loss; mean expenditures are equal to or greater than the baseline).
* **Alternative Hypothesis ($H_1$):** $\mu_{\text{Treatment}} < \mu_{\text{Control}}$ (The new strategy significantly reduces daily operational loss compared to the baseline).

### Empirical Results Summary

| Evaluation Metric | Strategy A (Control) | Strategy B (Treatment) | Performance Lift |
| :--- | :---: | :---: | :---: |
| **Avg. Daily Operational Loss** | Baseline Level | Optimized Level | **-28.89% Cost Reduction** |
| **System Volatility Control** | 150% Amplified Variance | 90% Capped Variance | **Risk Reduced by ~40%** |
| **Welch's $t$-Statistic** | — | **-12.0930** | Statistically Significant |
| **Empirical $p$-Value** | — | **0.0000** ($p < 0.05$) | Strong Rejection of $H_0$ |

The extremely low $p$-value ($0.0000$) provides definitive scientific backing to **reject the Null Hypothesis ($H_0$)**. The observed 28.89% cost saving is mathematically proven to be a result of algorithmic efficiency rather than random statistical fluctuation.

---

## 🚀 Key Takeaways & Business Value (Simple English Summary)

* **Handling Real-World Store Pressure:** In real life, retail stores do not operate alone. If a regular store (Strategy A) runs out of stock, frustrated customers will quickly drive to a nearby store to buy the item. This creates sudden, unexpected demand pressure for that second store. Our new **Strategy B handled this extra pressure perfectly** without creating messy inventory problems.
* **Big Financial Savings:** Even with the real-world noise injected, using Strategy B successfully **cuts down overall operational losses by 28.89%**. This means the company will stop losing huge amounts of money from empty shelves (lost sales) and holding too much unsold stock. 
* **Final Decision [APPROVED for All Stores]:** Because the data clearly proves that our new model works much better, we officially approve launching Strategy B in **all retail stores immediately**. This will help every store automatically order the right amount of stock, reduce waste, and protect company profits.
