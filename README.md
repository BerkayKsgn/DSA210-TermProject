# DSA210-TermProject

I am Berkay Kesgin, a student from Sabancı University, and this is my DSA210 (Introduction to Data Science) Term Project.
In this project, I will analyze the relationship between coffee and water consumption and their effects on focus duration and sleep patterns, supported by my collected data.

# Table of Contents

1. [Project Overview](#project-overview)  
2. [Objectives](#objectives)  
3. [Motivation](#motivation)  
4. [Data Collection & Sources](#data-collection--sources)  
5. [Data Preprocessing](#data-preprocessing)  
6. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
7. [Hypothesis Testing](#hypothesis-testing)  
8. [Conclusion](#-conclusion)
   
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

#  Hypothesis Testing

##  Hypothesis 1 — Does high coffee intake reduce sleep duration?

**Null Hypothesis (H₀):** There is no difference in sleep duration between high coffee days (>600ml) and low coffee days.  

**Alternative Hypothesis (H₁):** Sleep duration is significantly lower on high coffee days.

- **T-statistic** = -3.304  
- **P-value** = 0.002  

✅ **Result:** Statistically significant at the 0.05 level.

**Interpretation:** On days I consumed more than 600 ml of coffee, my sleep duration significantly dropped. This suggests high caffeine intake may impair sleep, likely due to its stimulant effect on the nervous system.

---

##  Hypothesis 2 — Does high water intake increase focus duration?

**Null Hypothesis (H₀):** Focus durations are the same regardless of whether I drank more than 1200ml of water.  

**Alternative Hypothesis (H₁):** Focus duration is higher on days with high water intake.

- **T-statistic** = -0.094  
- **P-value** = 0.926  

❌ **Result:** Not statistically significant.

**Interpretation:** Despite a common belief that better hydration leads to higher cognitive performance, my data did not show a significant difference in focus duration on high-water days.

---

##  Hypothesis 3 — Does high sugar intake negatively affect focus?

**Null Hypothesis (H₀):** Focus duration does not differ between high sugar (>35mg) and low sugar days.  

**Alternative Hypothesis (H₁):** Focus duration is significantly lower on high sugar intake days.

- **T-statistic** = 2.286  
- **P-value** = 0.029  

✅ **Result:** Statistically significant at the 0.05 level.

**Interpretation:** When my sugar intake exceeded 35 mg (mostly via sweetened coffee), my focus durations were significantly shorter. This may indicate that sugar spikes and subsequent energy crashes can hinder sustained cognitive performance, despite caffeine intake.

---

# Conclusion

This project analyzed the impact of daily coffee, water, and sugar intake on focus and sleep using self-tracked data over 40+ days. Hypothesis testing and visualization techniques were applied to explore potential patterns and causality.

---

##  Hypothesis 1 — High Coffee Intake Reduces Sleep Duration  

- **T-statistic:** -3.304  **P-value:** 0.002  

✅ **Statistically significant**

**Insight:** On days when I consumed over 600ml of coffee, I experienced a significant decrease in sleep duration. This supports the well-known stimulant effects of caffeine, especially when consumed later in the day.

---

##  Hypothesis 2 — High Water Intake Increases Focus Duration  

- **T-statistic:** -0.094  **P-value:** 0.926  

❌ **Not statistically significant**

**Insight:** Hydration is often associated with better cognitive performance, but my data did not support this link. Focus durations were similar regardless of water intake levels.

---

##  Hypothesis 3 — High Sugar Intake Negatively Affects Focus  

- **T-statistic:** 2.286  **P-value:** 0.029  

✅ **Statistically significant**

**Insight:** Higher sugar intake (>35mg) was associated with shorter focus durations. This suggests that excessive sugar, often consumed through sweetened coffee, may counteract the positive effects of caffeine on productivity.

---

##  Final Thoughts

- **Coffee** significantly reduced sleep duration, supporting its alertness-promoting nature, but with potential sleep tradeoffs.  
- **Water** did not show measurable cognitive benefits in this dataset, though its effects may be more subtle or long-term.  
- **Sugar**, when consumed in higher quantities, **reduced productivity** and may impair concentration.  

##  Suggestions for Further Study

- Track physical activity, stress levels, or meal timing as confounding variables.
- Apply regression models to quantify the individual contribution of variables.
- Expand the dataset beyond a single person and over a longer time frame for broader generalization.
