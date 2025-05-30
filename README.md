# DSA210-TermProject

I am Berkay Kesgin, a student from Sabancı University, and this is my DSA210 (Introduction to Data Science) Term Project.
In this project, I will analyze the relationship between coffee and water consumption and their effects on focus duration and sleep patterns, supported by my collected data.

# Table of Contents

1. [Project Overview](#project-overview)  
2. [Objectives](#objectives)  
3. [Motivation](#motivation)  
4. [Data Collection & Sources](#data-collection)  
5. [Data Preprocessing](#data-preprocessing)  
6. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
7. [Hypothesis Testing](#hypothesis-testing)  
8. [Conclusion](#conclusion)
9. [Machine Learning](#machine-learning-ml-analysis)
   
# Project Overview

Coffee is often associated with improved focus and productivity, while excessive intake may disrupt sleep. Likewise, proper hydration plays a crucial role in cognitive performance and well-being. But how do these factors interact?

This project aims to uncover the real impact of coffee and water consumption on focus and sleep quality using data-driven analysis. Over the next months, I will systematically track my daily intake, analyze focus patterns, and identify trends in sleep efficiency to better understand these relationships.

# Objectives

**Understanding the Impact of Beverage Consumption on Focus & Sleep**
- Analyze how coffee and water intake influence focus duration and sleep quality.
- Assess whether coffee timing affects sleep efficiency.
- Determine if higher water intake enhances cognitive performance and sleep duration.

**Applying Data Science Techniques**
- Conduct statistical analysis and hypothesis testing.
- Use data visualization to identify trends and correlations.
- Apply DSA210 concepts to a real-world dataset based on personal habits.

# Motivation

**Personal Curiosity**

I have always wondered if my focus levels and sleep patterns are truly affected by coffee and water intake or if it is just a perception.
This project will help me identify whether my habits influence my cognitive performance and sleep quality. By systematically collecting and analyzing data, I can determine if there are noticeable trends or if external factors play a bigger role than I assumed.

**Data-Driven Decision Making**

Rather than relying on assumptions, I want to use quantifiable data to answer these questions. Tracking my daily coffee and water intake, focus duration, and sleep efficiency will provide objective insights into my habits. This process will also encourage me to be more mindful of my consumption patterns and their effects.

**Applying Data Science in Real Life**

This project allows me to apply the skills I’ve learned in DSA210 to a real-world dataset that directly impacts my daily life. By using statistical analysis, hypothesis testing, and visualization techniques, I will uncover meaningful correlations and refine my ability to analyze complex behavioral data.

Ultimately, my goal is to identify actionable insights that help me optimize my routines for better focus, productivity, and sleep quality.

# Data Collection

## **Beverage Consumption**
- **Coffee Intake (ml):** Total amount of coffee consumed that day, manually recorded.
- **Caffeine Intake (mg):** Estimated caffeine amount based on the type and volume of coffee.
- **Water Intake (ml):** Total amount of water consumed per day.
- **Sugar Intake from Coffee (mg):** Amount of sugar added to coffee, manually recorded.

## **Focus and Cognitive Performance**
- **Focus Duration (min):** Total time spent in focused work, measured using the Pomodoro technique.
- **Screen Time (min):** Total daily screen time, recorded via phone settings.

## **Sleep Patterns**
- **Sleep Start Time:** The exact time the user went to sleep, recorded from a smartwatch.
- **Sleep End Time:** The exact time the user woke up, recorded from a smartwatch.
- **Total Sleep Duration (hours):** The total duration of sleep for that night, retrieved from a smartwatch.
- **Sleep Quality (%):** Percentage-based metric evaluating sleep efficiency, recorded from a smartwatch.
- **Last Coffee Intake Before Bed (hours before sleep):** Time elapsed between the last coffee consumed and sleep onset.

## **Environmental Factors**
- **Ambient Temperature (°C):** The daily average temperature, retrieved from a weather API.

# Data Preprocessing

The preprocessing was performed in data_process.ipynb, and the cleaned dataset is stored as cleaned_focus_sleep_data.xlsx.

- Datetime Parsing: Sleep start/end times were converted to datetime format to calculate Sleep (hrs).
- Feature Engineering: New binary columns were added:
  -	High Coffee → coffee > 600 ml
  -	High Water → water > 1200 ml
  -	High Focus → focus > 300 minutes

- Time Features: Extracted Sleep Start Hour and Sleep End Hour for pattern analysis.
- Column Reordering: Columns were rearranged for better readability and analysis compatibility.
- Missing Value Check: No null values were found in the final dataset.

  
#  Exploratory Data Analysis (EDA)

## 1. Variable Distributions

### • Distribution of Daily Focus Duration  
Displays how focus time is distributed across days.
  
![Focus Distribution](images/Distribution%20of%20Daily%20Focus%20Duration.png)

---

### • Distribution of Daily Water Intake  
Illustrates water consumption per day. Helps assess hydration habits and detect outliers.
  
![Water Distribution](images/Distribution%20of%20Daily%20Water%20Intake.png)

---

### • Distribution of Daily Sleep Hours  
Shows how many hours of sleep were recorded per day. Peaks can reveal common sleep durations (e.g., 6–8 hours).
  
![Sleep Distribution](images/Distribution%20of%20Daily%20Sleep%20Hours.png)

---

### • Distribution of Daily Coffee Intake  
Visualizes the distribution of daily coffee consumption. Useful for identifying high caffeine days and potential overconsumption patterns.
  
![Coffee Distribution](images/Distribution%20of%20Daily%20Coffee%20Intake.png)

---

##  2. Time Trends & Correlation Patterns

### • Focus and Sleep Duration Over Time  
A dual-axis line chart that visualizes how focus (in minutes) and sleep (in minutes) fluctuate day by day.

![Focus and Sleep Over Time](images/Focus%20and%20Sleep%20Duration%20Over%20Time%20(in%20Minutes).png)

---

### • Correlation Between Key Variables  
Displays Pearson correlation coefficients between coffee, water, sleep, and focus variables.  
Blue means negative correlation, red means positive. Helps identify strong linear relationships.

![Correlation Heatmap](images/Correlation%20Between%20Focus%2C%20Sleep%20and%20Consumption%20Variables.png)

---

##  3. Sugar Intake and Focus Duration

### • Distribution of Focus Duration by Sugar Intake  
Histogram comparing focus levels for high-sugar (red) vs low-sugar (blue) days.  
Highlights how added sugar might influence cognitive performance.

![Sugar Histogram](images/Distribution%20of%20Focus%20Duration%20by%20Sugar%20Intake.png)

---

### • Correlation Between Sugar Intake and Focus Duration  
Heatmap showing the linear relationship between sugar and focus.

![Sugar Correlation](images/Correlation%20Between%20Sugar%20Intake%20and%20Focus%20Duration.png)

---

### • Focus Duration vs High Sugar Intake (Boxplot)  
Boxplot comparison of focus levels between days with high (>35mg) and low sugar.  
Shows that sugar-heavy days might reduce focus consistency.

![Boxplot](images/Focus%20Duration%20vs%20High%20Sugar%20Intake.png)

---

### • Individual Focus Durations by Sugar Group  
Each dot represents daily focus minutes, grouped by sugar category.  
Shows how outliers and trends differ between high and low sugar consumption.

![Scatterplot](images/Individual%20Focus%20Durations%20by%20Sugar%20Group.png)

---

##  4. Water & Coffee Effects on Sleep and Focus

### • Focus Duration vs High Water Intake  
Compare focus durations between days with more or less than 1200 ml of water.  
Helps assess the potential impact of hydration on productivity.

![Water Focus](images/Focus%20Duration%20vs%20High%20Water%20Intake.png)

---

### • Effect of High Coffee Intake on Sleep Duration  
Boxplot showing how sleep hours vary depending on coffee intake (>600 ml).  
High coffee days show shorter and more varied sleep durations.

![Coffee Sleep](images/Effect%20of%20High%20Coffee%20Intake%20on%20Sleep%20Duration.png)

---

# Hypothesis Testing

## Hypothesis 1 — Does high coffee intake reduce sleep duration?

**Null Hypothesis (H₀):** There is no difference in sleep duration between high coffee days (>600ml) and low coffee days.  
**Alternative Hypothesis (H₁):** Sleep duration is significantly lower on high coffee days.

- **T-statistic:** -3.304  
- **P-value (one-sided):** 0.001  

✅ **Result:** Statistically significant at the 0.05 level.

**Interpretation:** On days I consumed more than 600 ml of coffee, my sleep duration significantly dropped. The one-sided test supports that high caffeine intake may impair sleep, likely due to its stimulant effect on the nervous system.

---

## Hypothesis 2 — Does high water intake increase focus duration?

**Null Hypothesis (H₀):** Focus durations are the same regardless of whether I drank more than 1200ml of water.  
**Alternative Hypothesis (H₁):** Focus duration is higher on days with high water intake.

- **T-statistic:** -0.094  
- **P-value (one-sided):** 0.537  

❌ **Result:** Not statistically significant.

**Interpretation:** The one-sided test does not provide evidence that high water intake increases focus. Despite a common belief that better hydration boosts cognitive performance, my data did not reflect a meaningful difference in focus duration.

---

## Hypothesis 3 — Does sugar intake affect focus duration?

**Null Hypothesis (H₀):** Focus duration is the same regardless of sugar intake (above or below 35 mg).  
**Alternative Hypothesis (H₁):** Focus duration differs significantly between high and low sugar intake days.

- **T-statistic:** 2.286  
- **P-value (two-sided):** 0.029  

✅ **Result:** Statistically significant at the 0.05 level.

**Interpretation:** The two-sided test reveals a significant difference in focus duration based on sugar intake. Interestingly, the result suggests that focus was actually higher on high sugar days — contrary to the original expectation that sugar would impair performance.

---

#  Conclusion

This project analyzed the impact of daily coffee, water, and sugar intake on sleep and focus using self-tracked data over 40+ days. Hypothesis testing and basic statistical techniques were applied to explore patterns and potential effects.

---

##  Hypothesis 1 — High Coffee Intake Reduces Sleep Duration  

- **T-statistic:** -3.304  **P-value:** 0.001  
✅ **Statistically significant**

**Insight:** On days when I consumed over 600 ml of coffee, I experienced a significant decrease in sleep duration. This supports the well-known stimulant effect of caffeine and its interference with sleep, especially when consumed late in the day.

---

##  Hypothesis 2 — High Water Intake Increases Focus Duration  

- **T-statistic:** -0.094  **P-value:** 0.537  
❌ **Not statistically significant**

**Insight:** Although hydration is often promoted as a factor in cognitive performance, this dataset did not show any statistically significant increase in focus duration with higher water intake.

---

##  Hypothesis 3 — Sugar Intake Affects Focus Duration  

- **T-statistic:** 2.286  **P-value:** 0.029  
✅ **Statistically significant**

**Insight:** Higher sugar intake (>35 mg), mostly through sweetened coffee, was associated with longer focus durations — opposite of the original hypothesis. This surprising result suggests that sugar's impact may vary based on context, or be confounded by other factors like caffeine synergy.

---

##  Final Thoughts

- **Coffee** clearly reduced sleep duration, validating its alertness-boosting but sleep-disruptive nature.  
- **Water** had no measurable impact on focus in this sample, suggesting effects may be subtle or long-term.  
- **Sugar**, rather than impairing focus, appeared to correlate with improved focus — highlighting the complexity of nutrition-cognition relationships.

---

##  Suggestions for Further Study

- Track additional variables such as physical activity, stress levels, meal timing, and caffeine time of day.  
- Apply regression models to isolate the effects of each variable.  
- Collect data over a longer period and across multiple individuals to improve generalizability.  
- Integrate physiological measures (e.g., heart rate, cortisol levels) for a more complete picture.

---

# Machine Learning (ML) Analysis

In this section, we apply **machine learning models** to better understand and predict how different daily habits—such as coffee, water, and sugar intake—affect **focus** and **sleep**. Each **hypothesis** is modeled and evaluated using relevant supervised learning techniques, including both **classification** and **regression**.

---

###  ML Objective

To supplement statistical hypothesis testing with **predictive modeling**, we used machine learning algorithms to:

- Classify whether a day would be **high focus** or not (binary classification)
- Predict **sleep duration** and **focus duration** using real-valued input features (regression)

By evaluating models on performance metrics such as **Accuracy**, **Recall**, **F1-Score**, **MAE**, **RMSE**, and **R²**, we aim to quantify how much predictive signal exists in our behavioral features.

---

### ML Hypotheses Modeled

| Hypothesis Code | Description                                         | Type         | Target Variable           |
|------------------|-----------------------------------------------------|--------------|----------------------------|
| **H1**           | Does high coffee intake reduce sleep duration?      | Regression   | `Sleep Duration (hrs)`     |
| **H2**           | Does high water intake increase focus duration?     | Regression   | `Focus Duration (min)`     |
| **H3**           | Does sugar intake affect focus classification?      | Classification | `High Focus (0/1)`       |

---

###  Models Used

- **Linear Regression**: for baseline regression analysis  
- **K-Nearest Neighbors (KNN)**: simple, distance-based classifier/regressor  
- **Random Forest**: an ensemble method for handling nonlinear relationships  
- **Logistic Regression**: probabilistic binary classifier (for H3 only)
 
###  How Results Are Presented

Each hypothesis below is explored in the following structure:

1.  **Problem Setup**  
   — What we're trying to predict, and why it matters

2.  **Model Training & Evaluation**  
   — Key metrics like MAE, RMSE, Accuracy, F1, R² Score

3.  **Visual Aids**  
   — Confusion matrices for classifiers  
   — Scatterplots and regression lines for regressors  
   — Bar charts comparing model performance side by side

4.  **Interpretation & Comparison**  
   — Which models performed best and why  
   — Whether the predictive results support or challenge the statistical hypothesis

---

## Machine Learning: Predicting Sleep Duration (H1)

### Hypothesis 1 — Does High Coffee Intake Reduce Sleep Duration?

This hypothesis explores whether **higher coffee intake is associated with reduced sleep duration**.

We treat this as a **regression problem**, modeling:

- **Input Feature (X):** Coffee Intake (ml)
- **Target Variable (Y):** Sleep Duration (hrs)

We tested three different regression models to predict how coffee consumption affects sleep:
- **Linear Regression**
- **KNN Regressor**
- **Random Forest Regressor**

---

### 📊 Visualizing the Relationship

Scatterplot showing the raw relationship between coffee intake and sleep duration:

![Coffee Intake vs Sleep Duration](images/Coffee%20intake%20vs%20sleep%20duration.png)

---

### 📈 Model 1: Linear Regression

A linear regression line was fitted to understand the trend.

- **Intercept (b₀):** 10.247  
- **Coefficient (b₁):** -0.003

> For every additional 100 ml of coffee, sleep duration drops by ~18 minutes.

**Evaluation Metrics:**

- MAE: 0.960  
- RMSE: 1.237  
- R² Score: 0.334

![Linear Regression — Coffee vs Sleep](images/lineer%20regression%20-%20coffee%20intake%20vs%20sleep%20duration.png)

---

### 📉 Model 2: KNN Regressor

The K-Nearest Neighbors Regressor model captured local patterns but performed poorly overall.

**Evaluation Metrics:**

- MAE: 62.78  
- RMSE: 65.14  
- R² Score: -0.004

![KNN Regressor — Actual vs Predicted](images/KNN%20Regressor-%20Actual%20vs%20Predicted%20Sleep%20Duration%20(H1).png)

---

### 🌲 Model 3: Random Forest Regressor

The Random Forest model performed better than KNN, capturing more complex relationships.

**Evaluation Metrics:**

- MAE: 50.03  
- RMSE: 55.24  
- R² Score: 0.278

![Random Forest — Actual vs Predicted](images/Random%20Forest-%20Actual%20vs%20Predicted%20Sleep%20Duration%20(H1).png)

---

### 📊 H1 Model Performance Comparison

The chart below compares the performance of all three models using MAE, RMSE, and R² Score:

![Model Performance Comparison on H1](images/Model%20Performance%20Comparison%20on%20H1-%20Coffee%20Intake%20vs%20Sleep%20Duration.png)

---

### Interpretation

- **Linear regression** had the best performance among the three, with the highest R² and lowest error.
- **KNN Regressor** struggled, likely due to the small sample size and lack of local structure.
- **Random Forest** improved upon KNN but didn’t outperform linear regression in this case.

📌 **Conclusion:**  
The models support the hypothesis that **coffee intake is negatively associated with sleep duration**, with linear regression providing the clearest evidence.

---

## Machine Learning: Predicting Focus Duration (H2)

### Hypothesis 2 — Does High Water Intake Increase Focus Duration?

This section tests the hypothesis that **increased water intake improves focus duration**.  
We model this using regression techniques to predict daily **focus duration (in minutes)** based on **water consumption (ml)**.

###  Models Applied

We evaluated three models for this hypothesis:

| Model               | MAE   | RMSE   | R² Score |
|---------------------|--------|--------|----------|
| Linear Regression   | 52.63  | 74.86  | 0.014    |
| KNN Regressor (k=3) | 48.22  | 58.96  | 0.178    |
| Random Forest       | 44.43  | 53.69  | 0.320    |

#### 📈 Model Comparison Chart

This grouped bar chart compares all three regression models using key error metrics (MAE, RMSE, R²).  
Random Forest performs the best with the lowest MAE and highest R² score.

![Model Comparison – H2](images/Model%20Performance%20Comparison%20on%20H2-%20Water%20Intake%20vs%20Focus%20Duration.png)

---

### 📉 Visualization – Raw Relationship

A simple scatterplot shows the raw relationship between **Water Intake (ml)** and **Focus Duration (min)**.  
The lack of strong visual trend supports our earlier statistical test result.

![Scatter – Water vs Focus](images/Water%20Intake%20vs%20Focus%20Duration.png)

---

### 📊 Linear Regression – Water vs Focus

This plot overlays the regression line on top of the scatterplot.  
The slope is slightly negative, and R² is very low (≈ 0.01), indicating a poor fit.

![Linear Regression – Water vs Focus](images/Linear%20Regression%20—%20Water%20vs%20Focus.png)

---

### 🔶 KNN Regressor – Actual vs Predicted

The following scatterplot compares actual vs predicted focus durations for KNN (k=3).  
Although there's slight clustering along the diagonal, large deviations remain.

📉 **KNN Regressor (H2 – Water vs Focus):**  
- MAE: 48.22  
- RMSE: 58.96  
- R² Score: 0.178

![KNN Predicted vs Actual – H2](images/KNN%20Regressor-%20Actual%20vs%20Predicted%20Focus%20Duration%20(H2).png)

---

### 🔵 Random Forest – Actual vs Predicted

This scatter plot compares actual vs predicted focus durations for the Random Forest Regressor.  
The fit is slightly better, but many points still lie far from the ideal diagonal.

📉 **Random Forest Regressor (H2 – Water vs Focus):**  
- MAE: 44.43  
- RMSE: 53.69  
- R² Score: 0.320

![Random Forest Predicted vs Actual – H2](images/Random%20Forest%20—%20Actual%20vs%20Predicted%20(H2).png)

---

###  Conclusion

Although **Random Forest performed best**, **all models had weak R² scores**, suggesting that **water intake alone is not a strong predictor** of focus duration.  
This aligns with our earlier hypothesis testing, which found **no significant difference** in focus between high and low hydration days.

🔍 **Future Improvement:**  
Combining water intake with **other features** (e.g., sleep quality, coffee intake, screen time) in a **multi-variable model** may yield better predictive power.

---

## Machine Learning: Predicting High Focus Days (H3)

###  Hypothesis 3 — Does Sugar Intake Affect Focus Duration?

To classify whether a day is a **high focus day** (focus duration > 300 min), we trained three classification models using behavioral data features such as:

- Sugar Intake  
- Coffee Intake  
- Water Intake  
- Sleep Duration  
- Screen Time  
- Ambient Temperature  

### 📌 Target Variable:
`High Focus (1 = Yes, 0 = No)`

---

### 🧪 Models Trained:

1. **Logistic Regression**
2. **K-Nearest Neighbors (K=5 and tuned K=2)**
3. **Random Forest Classifier**

Each model was evaluated on **Accuracy**, **Recall**, and **F1-Score**.

---

### 🔍 Model Comparison Chart

The bar chart below compares the performance of all models:

![Model Comparison](images/Model%20Performance%20Comparision%20H3.png)

---

### ✅ Logistic Regression

**Confusion Matrix:**

![Confusion Matrix - Logistic Regression](images/Confusion%20Matrix%20-%20Logistic%20Regression.png)

- **Accuracy:** 0.56  
- **Precision (High):** 0.60  
- **Recall (High):** 0.60  
- **F1-Score (High):** 0.60

🧠 **Interpretation:**  
Logistic regression offered balanced performance with solid generalization. Coefficients can also be interpreted for feature importance.

---

### ✅ K-Nearest Neighbors (K = 5)

**Confusion Matrix:**

![Confusion Matrix - KNN (k=5)](images/Confusion%20Matrix%20-%20KNN%20(k=5).png)

- **Accuracy:** 0.22  
- **Recall (High):** 0.40  
- **F1-Score (High):** 0.36

---

### ✅ K-Nearest Neighbors (Tuned K = 2)

**Confusion Matrix:**

![Confusion Matrix - KNN (k=2)](images/Confision%20Matrix%20-%20KNN%20(k=2).png)

- **Accuracy:** 0.56  
- **Recall (High):** 0.40  
- **F1-Score (High):** 0.36

🧪 **Interpretation:**  
After tuning, KNN improved in accuracy, but recall and precision remained lower than Logistic Regression.

---

### ✅ Random Forest Classifier

**Confusion Matrix:**

![Random Forest Confusion Matrix](images/Random%20Forest%20Confision%20Matrix.png)

- **Accuracy:** 0.33  
- **Recall (High):** 0.60  
- **F1-Score (High):** 0.50

🌲 **Interpretation:**  
Random Forest managed to **recall most high focus days**, but performance on low focus days was weak. Great for minimizing false negatives.

---

### 📊 Summary

| Model               | Accuracy | Recall (High) | F1-Score (High) |
|--------------------|----------|----------------|------------------|
| Logistic Regression | 0.56     | 0.60           | 0.60             |
| KNN (k=2)           | 0.56     | 0.40           | 0.36             |
| Random Forest       | 0.33     | 0.60           | 0.50             |

---

### 🧩 Conclusion

- **Logistic Regression** achieved the most balanced classification performance.
- **Random Forest** had strong recall, useful when minimizing false negatives (missing high focus days).
- **KNN**, though simple, struggled with generalization unless properly tuned.

---
