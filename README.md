# Titanic Dataset - Exploratory Data Analysis (EDA)

This repository contains an Exploratory Data Analysis (EDA) of the classic Titanic training dataset (`train.csv`). The objective of this notebook is to inspect the data, handle missing values, and perform univariate analysis to uncover patterns and distributions among the passengers.

## Overview
Understanding the passenger demographics and ticket features is a crucial first step before building any predictive models for the Titanic dataset. This project focuses strictly on data wrangling and visualization, transforming raw data into actionable insights.

## Technologies & Libraries
This analysis was conducted using Python and the following data science libraries:
*   **`pandas`**: For data ingestion, manipulation, and cleaning.
*   **`numpy`**: For numerical and array operations.
*   **`matplotlib.pyplot`**: For structuring and plotting static visualizations.
*   **`seaborn`**: For creating statistical, aesthetically pleasing plots (e.g., KDEs, count plots).

## Data Inspection & Cleaning
Proper data types and complete data are essential for accurate analysis. The following cleaning steps were applied:
1.  **Missing Age Values:** The `Age` column was missing ~19.8% of its data (177 null values)[cite: 1]. Since the age distribution closely followed a normal distribution (skewness ~0.38), the missing values were imputed using the overall mean age[cite: 1]. The column was then converted to an integer datatype[cite: 1].
2.  **Missing Cabin Data:** Null values in the `Cabin` column were filled with a placeholder string `'M'` (Missing)[cite: 1].

## Key Insights & Visualizations
Through univariate analysis, several key observations were made regarding the passengers:

*   **Age Distribution:** Histograms and KDE plots indicate that the majority of passengers were between 20 and 30 years old. Boxplots confirmed that while there were elderly passengers (up to 80 years old), these were valid entries rather than outliers.
*   **Fare Distribution:** The fare prices are highly right-skewed (positive skewness of ~4.78). Approximately 50% of the passengers paid less than $14, while the majority paid between $0 and $25. High fares (e.g., >$250) exist but represent valid grouped ticket purchases for families rather than data errors.
*   **Survival Rate:** A pie chart and count plot visualization revealed that only 38.4% of the passengers in this dataset survived the disaster.
*   **Gender:** A standard count plot was generated to observe the overall distribution of male and female passengers onboard.

##  Feature Engineering
To better understand passenger groupings, a new feature was created:
*   **FamilySize:** By visualizing and merging the `SibSp` (siblings/spouses) and `Parch` (parents/children) columns, a unified `FamilySize` feature was generated (`SibSp` + `Parch` + 1). This new metric provides a clearer picture of whether a passenger was traveling alone or with a large family.
*   **FamilyType:** This new metric provides a clearer picture of whether a passenger was traveling alone or with a large family.
*   **Deck:** Classifying people surivival rate 
