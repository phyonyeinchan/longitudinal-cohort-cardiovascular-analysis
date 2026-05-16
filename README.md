# 📈 Traditional Epidemiological Analysis: Longitudinal Cohort & Survival Analysis

## 📌 1. Project Title
**Longitudinal Cohort Modeling and Time-to-Event Survival Analysis of Sleep and Lifestyle Predictors in Cardiovascular Epidemiology.**

---

## 🔍 2. Background & Objectives
Longitudinal cohort registers act as the golden standard in Nordic healthcare registries (such as Swedish national records) to decipher the temporal effects of risk factors. This computational study implements classic advanced epidemiology models to measure time-dependent risk trajectories.
The core objectives of this research project are:
- To evaluate how sleep architecture influences the duration of **CVD-free survival probability** over a 15-year horizon.
- To quantify adjusted hazards utilizing multivariate **Cox Proportional Hazards Regression**.
- To estimate the exact clinical net lifespan loss via **Restricted Mean Survival Time (RMST)** modeling.
- To validate survival models using structural residue diagnostics and account for longitudinal dropouts via **Cumulative Incidence Functions (CIF)**.

---

## 📂 3. Longitudinal Register Specifications
- **Cohort Architecture:** Synthesized continuous time-to-event longitudinal registry (n=500 cases).
- **Temporal Bound:** Maximum 15-year longitudinal follow-up spectrum.
- **Risk Metrics tracked:** Age, Biological Gender, Systolic Blood Pressure, Smoking Habits, and Categorized Sleep Profiles.
- **Endpoints:** Time-to-event vector (`FollowUp_Years`) alongside discrete cardiovascular incidence flags (`CVD_Event`).

---

## 🛠️ 4. Advanced Epidemiology Methods Deployed
The survival workflow is constructed using the `survival`, `survminer`, `survRMST`, and `cmprsk` pipelines in R:
1. **Longitudinal Censoring Handling:** Adjusted time-to-event intervals for subjects censored or dropped before endpoint detection.
2. **Kaplan-Meier Estimator:** Computed non-parametric probability curves stratified by sleep traits, verified via formal Log-Rank testing.
3. **Multivariate Cox Regression:** Modeled clinical hazard forces to yield adjusted Hazard Ratios (HR) with corresponding 95% Confidence Intervals.
4. **Interaction Hazard Assessment:** Tested for compound sex-specific longitudinal modifications ($Gender \times Sleep$).
5. **Strict Proportional Hazards Diagnostics:** Executed global and feature-specific **Schoenfeld Residuals Tests** via `cox.zph()` to confirm model mathematical invariance.
6. **Lifespan Translation (RMST Analysis):** Applied `rmst2()` to calculate the distinct absolute loss of disease-free years over a restricted temporal window.
7. **Competing Risk Adjustment:** Formulated Cumulative Incidence Functions (CIF) via `cuminc()` to preserve diagnostic accuracy against classical overestimations.

---

## 🏆 5. Primary Epidemiological Insights
- **Accelerated Hazard Trajectories:** The Kaplan-Meier profile and Log-Rank statistics verified that individuals with shortened sleep exhibit significantly rapid declines in CVD-free survival probability over 15 years ($p < 0.05$).
- **Independent Predictive Hazards:** Multivariate Cox models confirmed that short sleep acts as a significant independent driver of incident cardiovascular events, even after controlling for traditional baseline modifiers like blood pressure and smoking status.
- **Resilient Model Validation:** The Schoenfeld residuals test generated non-significant global p-values ($p > 0.05$), confirming that the proportional hazard conditions are fully intact and robust across time blocks.
- **Quantifiable Life-Year Margins:** RMST delta vectors successfully extracted the net clinical temporal loss induced by chronic sleep deprivation, translating risk metrics into absolute years.

---

## 💻 6. Technical Stack Requirements
- **Language & Libraries:** R (v4.6.0) / `survival`, `survminer`, `survRMST`, `cmprsk`, `tidyverse`

---

## 🔗 7. Live Interactive Report
[👉 CLICK HERE TO VIEW THE FULL INTERACTIVE LONGITUDINAL REPORT]https://phyonyeinchan.github.io/longitudinal-cohort-cardiovascular-analysis/
