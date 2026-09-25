# Data Exploration and Visualization – Student Habits vs Academic Performance

## ▸ Project Overview
- **Exploratory data analysis:** structured investigation of a student habits dataset
- **Feature understanding:** distributions, relationships, and data quality checks across numeric and categorical variables
- **Insight-driven focus:** analysis aimed at identifying what predicts exam performance

## ▸ Tech Stack
- **Language:** Python
- **Data analysis:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Workflow:** Jupyter Notebook (VS Code)

## ▸ Project Context
- **Academic origin:** university project (IU International University of Applied Sciences, Exploratory Data Analysis and Visualization)
- **Design goal:** applied EDA workflow, with colour and plot choices grounded in data visualization theory

---

## 1. Dataset Overview

**Source**: [Student Habits vs Academic Performance](https://www.kaggle.com/datasets/jayaantanaath/student-habits-vs-academic-performance) (Kaggle)

1,000 student records, 16 variables. Explicitly described by its creator as a simulated dataset, generated to reflect realistic patterns rather than drawn from actual student records.

**Main Columns**:
- `exam_score`: outcome variable
- `study_hours_per_day`, `social_media_hours`, `netflix_hours`, `sleep_hours`, `exercise_frequency`, `attendance_percentage`: numeric predictors
- `age`, `gender`: demographics
- `part_time_job`, `extracurricular_participation`: binary categorical
- `diet_quality`, `internet_quality`, `parental_education_level`: ordinal categorical
- `mental_health_rating`: 1-10 scale

---

## 2. Project Objectives

- Clean and prepare the dataset for analysis
- Describe location, variance, and distribution of key numeric variables
- Test relationships between behavioural, lifestyle, and demographic factors and exam performance
- Use colour and plot type deliberately, matched to each variable's type (nominal, ordinal, continuous)
- Compare findings against an independent analysis of the same dataset

---

## 3. Data Processing

- Confirmed data types, column naming, and duplicate records
- Verified semantic consistency (combined daily activity hours never exceed 24; percentage and rating columns within expected bounds)
- Missing values in `parental_education_level` (9.1%) assigned to a separate "Unknown" category, rather than dropped or imputed
- Outliers identified via IQR but retained, as plausible individual variation rather than data errors

---

## 4. Exploratory Analysis

### 4.1 Sample Overview
- Univariate distributions of all numeric and categorical variables
- Age, exercise frequency, and mental health rating show flat, near-uniform shapes; study hours and exam score both form well-shaped bell curves
- Gender shows no meaningful relationship with exam score

### 4.2 Study Hours as the Dominant Predictor
- Strongest relationship in the dataset: Pearson correlation of 0.83 with exam score
- Confirmed consistently across distribution, scatterplot with regression line, and binned averages by study-hour range

### 4.3 Correlation Across Variables
- Full correlation matrix across numeric and appropriately encoded categorical variables (binary/ordinal mapped to preserve order; nominal one-hot encoded)
- Mental health rating: 0.32. Exercise frequency: 0.16. Sleep hours: 0.12. Social media and Netflix hours: -0.17 each. All remaining variables below 0.2 in magnitude

### 4.4 Mental Health, Lifestyle, and Categorical Factors
- Mental health rating shows a genuine, moderate link to performance (12.5-point gap between lowest and highest wellbeing bands)
- Diet quality and internet quality, both ordinal, do not produce an ordinal effect on exam score, the middle category outperforms the highest in both cases, a pattern invisible to correlation alone and only recoverable through direct visualization

### 4.5 Comparison with an Independent Analysis
- An independent Kaggle notebook on the same dataset confirms the study hours and screen time findings, but describes mental health rating as showing "almost zero correlation," despite it computing to 0.32 here, a divergence attributed to judging correlation strength by eye rather than computing it directly

---

## 5. Conclusion

Study hours per day is, by a wide margin, the strongest predictor of exam performance in this dataset. Mental health rating is a real secondary factor; exercise, sleep, and screen time show weaker but genuine effects. Categorical background factors, including two ordinal variables, diet and internet quality, show weak and in some cases non-monotonic relationships with performance, illustrating a real limitation of correlation coefficients: they can miss patterns that only become visible through direct visualization. Since the dataset is explicitly simulated, these findings describe the logic of the simulation rather than verified real-world student behaviour.

---

## Data & Attribution

This analysis is based on a publicly available, simulated dataset, used here for academic and analytical purposes.
