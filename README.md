# A/B/n Testing: Optimizing Conversion Funnels via Button UX

## 📌 Project Overview
The objective of this project was to optimize the Click-Through Rate (CTR) of Eniac’s homepage primary banner. Following user feedback indicating that the original "SHOP NOW" text felt like "too immediate a commitment," I analyzed an **A/B/n test** (run from Nov 2 to Nov 16, 2021) comparing four variations of button color and text to identify the optimal balance between visual salience and messaging.

---

## 📊 Key Business & Statistical Insights

### 1. The Color Dominance Effect
Analysis confirms that visual features (Color) were a much stronger driver of engagement than CTA semantics (Text). 
* **White buttons** significantly outperformed red ones, achieving a CTR of **~2.0-2.1%**.
* **Red buttons** led to a sharp decline in performance, with CTR dropping as low as **~0.76%**.

<p align="left">
  <img src="images/ctr-with-intervals.png" width="600" alt="CTR Confidence Intervals">
</p>
<p align="left"><em>Figure 1: CTR with 95% Confidence Intervals</em></p>

### 2. Strategic "Post-Hoc" Significance
While the overall test showed a difference, I performed a **Post-hoc analysis with Bonferroni correction** ($p_{threshold} = 0.0083$) to isolate the winner. The matrix reveals that the difference between "SHOP NOW" (A) and "SEE DEALS" (C) is **statistically insignificant** ($p = 0.465$), meaning we cannot guarantee a lift by switching texts.

<table border="0">
  <tr>
    <td width="100%" valign="middle">
      <img src="images/matrix(p-value).png" width="80%" alt="Statistical Significance Matrix">
      <p align="center"><em>Figure 2: Statistical Significance Matrix (p-values)</em></p>
    </td>
  </tr>
</table>

---

## 🛠️ Tech Stack & Methodology
* **Language:** Python (Pandas, NumPy)
* **Statistics:** Hypothesis Testing ($\chi^2$), Post-hoc Analysis (Bonferroni Correction), Confidence Intervals
* **Visualization:** Matplotlib, Seaborn
* **Domain:** E-commerce / Conversion Rate Optimization (CRO)

## 📂 Project Structure
* `abn-testing-ux-hypothesis.ipynb` — Full Python pipeline including data cleaning, Chi-square testing, and statistical visualization.
* `images/` — Directory containing key statistical plots used in this report.

---

## 💡 Final Conclusion & Strategic Recommendations

### Key Findings
* **Color Impact**: The experiment conclusively proved that **white buttons are the superior visual choice** for Eniac’s primary banner. Red variations (B and D) caused a massive drop in engagement, reducing CTR by up to **62%** compared to the control group.
* **The "Text Lift" Illusion**: While Variation C ("SEE DEALS") achieved the highest raw CTR (**2.12%**), the observed lift over Variation A (**2.02%**) is only **~5%**. This falls significantly short of our **20% Minimum Detectable Effect (MDE)** target.

* **Statistical Verdict**: The difference between "SHOP NOW" (A) and "SEE DEALS" (C) is **statistically insignificant** ($p = 0.465$). From a data perspective, Variation C is currently performing identical to the baseline.

### Recommendations
* **Immediate Action**: **Permanently reject the implementation of red buttons**. They are visually disruptive and clearly harmful to the conversion funnel.
* **Product Decision**: **Maintain Variation A as the default**. Switching to Variation C is not recommended at this time because the observed gain is statistically indistinguishable from noise and fails to meet the business success criteria (20% lift).
