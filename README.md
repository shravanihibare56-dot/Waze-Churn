# Waze User Churn & Engagement Analysis: Hypothesis Testing by Device Type

## Project Overview
This project is **Milestone 4** of the **Waze User Churn Analytics** initiative, aimed at driving overall platform growth by preventing monthly user churn and improving retention. Using Python, exploratory data analysis (EDA) and a two-sample independent $t$-test were conducted to evaluate whether user driving engagement differs significantly between **iPhone** and **Android** users.

---

## Business Problem & Research Question
To better understand user behavior and make data-backed inferences about the broader Waze user base, the data team evaluated the relationship between device type and app usage frequency (measured by the number of drives).

* **Research Question:** *Do drivers who open the Waze application using an iPhone have the same number of drives on average as drivers who use Android devices?*

---

## Methodology (PACE Framework)
1. **Plan:** Defined the research question, formulated the null ($H_0$) and alternative ($H_A$) hypotheses, and established a 5% significance level ($\alpha = 0.05$).
2. **Analyze:** Loaded `waze_dataset.csv`, encoded the categorical `device` column (`iPhone` = `1`, `Android` = `2`) into a numerical `device_type` variable, and calculated group-level descriptive statistics.
3. **Construct:** Segmented the `drives` distributions for iPhone and Android cohorts and executed a two-sample independent Welch's $t$-test (`scipy.stats.ttest_ind(..., equal_var=False)`).
4. **Execute:** Evaluated the $t$-test outcome against the significance threshold ($\alpha = 0.05$) and compiled an executive summary with actionable next steps for the Waze leadership team.

---

## Exploratory Data Analysis (EDA)
Comparing the average number of drives across both device categories showed a slight difference in sample means:

| Device Type | Encoded Label | Exact Mean Drives | Rounded Mean (Executive Summary) |

 **iPhone** | `1` | `67.86` (`67.859078`) | **68** |
 **Android** | `2` | `66.23` (`66.231838`) | **66** |

* **Initial Observation:** Within the sample data, iPhone drivers recorded a slightly higher average number of drives (~1.63 more drives) than Android drivers. Hypothesis testing was conducted to determine whether this observed gap reflects a true population difference or random sampling variation.

---

## Hypothesis Testing
* **Null Hypothesis ($H_0$):** There is no difference in the average number of drives between drivers who use iPhone devices and drivers who use Android devices ($\mu_{\text{iPhone}} = \mu_{\text{Android}}$).
* **Alternative Hypothesis ($H_A$):** There is a difference in the average number of drives between drivers who use iPhone devices and drivers who use Android devices ($\mu_{\text{iPhone}} \neq \mu_{\text{Android}}$).
* **Significance Level ($\alpha$):** `0.05` (5%)

### Statistical Conclusion
* **Test Method:** Two-Sample Independent $t$-test (Welch's $t$-test, `equal_var=False`)
* **Result ($p\text{-value} > 0.05$):** **Fail to reject the null hypothesis ($H_0$).**
* **Interpretation:** There is **no statistically significant difference** in the mean number of drives between iPhone users and Android users.

---

## Key Insights & Recommendations
* **Consistent Engagement Across Platforms:** Even though iPhone users show a marginally higher sample average, driving behavior across iPhone and Android platforms is statistically consistent.
* **Expand Hypothesis Testing:** Conduct additional two-sample $t$-tests across other behavioral and usage variables in the dataset to identify stronger predictors of user engagement and churn.
* **UI & Marketing Experimentation:** Since core driving engagement is similar across both device types, test temporary changes in marketing campaigns or user interface (UI) features to gather richer behavioral data and investigate churn drivers.

---

## Tech Stack & Repository Structure
* **Language:** Python 3
* **Libraries:** `pandas`, `scipy.stats`
* **Repository Files:**
  * `Activity_Course 4 Waze project lab.ipynb` — Jupyter Notebook containing data preparation, descriptive statistics, and hypothesis testing.
  * `waze_dataset.csv` — Dataset capturing Waze user activity, drive counts, and device types.
  * `Executive_Summary.pdf` — Stakeholder summary presenting Milestone 4 results and recommendations to Waze leadership.

---

## Author
**Shravani Satish Hibare**  
Data Analyst 
