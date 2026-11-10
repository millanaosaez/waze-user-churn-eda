#  Waze User Churn Project: Exploratory Data Analysis (EDA)

Repository corresponding to Course 2 (Go Beyond the Numbers: Translate Data into Insights) of the Data Analytics Professional Certificate program, focusing on exploratory data analysis (EDA) and visualization applied to Waze navigation app user behavior.

---

##  Project Context

The Waze data analytics team is in the early stages of an enterprise project focused on predicting and mitigating user churn. 

Under the supervision of Chidi Ga (Senior Data Analyst) and with the goal of presenting executive results to Harriet Hadzic (Director of Data Analysis), this notebook documents the inspection, cleaning, statistical analysis, and visualization process of user behavior patterns to transform raw data into actionable insights.

---

##  Methodological Framework: The PACE Framework

The project is structured under the PACE problem-solving framework:

1. **Plan:** Definition of objectives, scope, and initial loading of libraries (`pandas`, `numpy`, `matplotlib`, `seaborn`) and the dataset (`waze_dataset.csv`).
2. **Analyze:** 
   - Structural inspection using `df.info()`, `df.describe()`, and `df.head()`.
   - Identification of missing values (e.g., 700 missing records in the `label` column).
   - Assessment of variable relevance: exclusion of the `ID` column due to lack of predictive value in user churn.
3. **Construct:**
   - Formal detection of outliers using box plots based on the Interquartile Range (IQR).
   - Generation of histograms to evaluate skewness and probability distributions of continuous variables (`sessions`, `drives`, `driven_km_drives`, etc.).
4. **Execute:** Synthesis of key findings for subsequent predictive modeling stages and executive communication.

---

##  Applied EDA Phases

Following data analytics best practices, the workflow covers the following analytical phases:

* **Discovering:** Initial loading, review of dimensions ($14,999$ rows $\times$ $13$ columns), and data type validation (`int64`, `float64`, `object`).
* **Structuring:** Verification of structural integrity and preparation of the dataset for univariate and bivariate analysis.
* **Cleaning & Validating:** Treatment of missing values in the target variable (`label`) and analysis of numeric variable distributions.
* **Statistical Testing & Visualizing:**
  * Generation of univariate and multivariate plots using `Seaborn` and `Matplotlib`.
  * Analysis of trends in monthly usage metrics (sessions opened, kilometers driven, active days, and driving days).

---

##  Key Findings & Insights

* **Distribution Skewness:** Variables such as `sessions`, `drives`, and `duration_minutes_drives` exhibit pronounced **right-skewness**. Most users record moderate usage, while a small percentage concentrates extreme values (legitimate high-activity outliers).
* **Usage Intensity:** The median monthly sessions stand at 56, while the estimated historical cumulative metric (`total_sessions`) shows a tight relationship suggesting that a significant proportion of user activity is concentrated in recent observation periods.
* **Active Days:** User behavior in terms of monthly active days shows wide dispersion, which will serve as a baseline to segment retained users versus churned users in subsequent statistical modeling phases.

---

##  Technologies & Libraries Used

* **Python** (Jupyter Notebook execution environment)
* **Pandas & NumPy** (Tabular data manipulation, cleaning, and structuring)
* **Matplotlib & Seaborn** (Advanced statistical visualization generation: histograms, box plots)

---

##  Notebook Structure

1. **Part 1:** Import libraries and load dataset (`waze_dataset.csv`).
2. **Part 2:** Initial data exploration, cleaning unnecessary columns (`ID`), and checking for nulls.
3. **Part 3:** Building analytical visualizations (histograms and box plots for anomaly detection).
4. **Part 4:** Evaluating results, documenting business strategy responses, and preparing for the executive report.