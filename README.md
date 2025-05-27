# Task 2 – Exploratory Data Analysis on Titanic Dataset 🚢

This repository contains Task 2 of the AI & ML Internship: Exploratory Data Analysis (EDA) using the Titanic Dataset.

Objective: Visually and statistically explore the Titanic dataset to uncover patterns, trends, anomalies, and key features relevant to survival.

---

## Project Contents

- `Titanic.csv` — Original dataset  
- `Visualization-statistics.py` — Python script for all preprocessing + visualizations  
- `output-image/` — Folder containing all visual plots  
- `README.md` — This documentation  

---

## Resources used

Dataset-Titanic.csv

## Tools Used

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib

---

## Data Preparation Summary

- Missing values in Age and Embarked were filled using median and mode.
- Cabin column dropped due to high missingness.
- New features created:
  - `FamilySize = SibSp + Parch + 1`
  - `Title` extracted from Name
- Rare titles grouped into a single 'Rare' category.

---

## Exploratory Data Analysis (EDA)

###  > Basic Distributions

#### Survival Count
Most passengers did not survive (label = 0).

####  Passenger Class Count
Most passengers were in 3rd class.

###  > Univariate Numeric Distributions

####  Age Distribution
- Majority of passengers were aged 20–40.
- Age distribution is slightly right-skewed.
- There are several children and elderly.
- ![Age distribution](https://github.com/user-attachments/assets/bb4935b4-028e-4cac-bd73-ca7df6cd7409)


####  Fare Distribution
- Fare is highly right-skewed.
- A few passengers paid extremely high fares (outliers).

####  Family Size
- Most passengers were either alone or had small family sizes.
- Medium family sizes (3–4) are relatively rare but important.

###  > Boxplots (Outlier Detection)

- Fare has extreme outliers beyond 300.
- Age and FamilySize distributions show mild outliers.
- Boxplots help reveal potential anomalies and distribution spread.

###  > Bivariate Analysis – Survival vs Features

#### Age by Survival
- Survivors tend to be slightly younger.
- More non-survivors are seen in the middle-aged group.
- ![Age Distribution by survival](https://github.com/user-attachments/assets/6fce846a-824b-4553-8d32-642a5db4e093)


#### Fare by Survival
- Survivors generally paid higher fares.
- Indicates wealth/class could have impacted survival.
- ![Fare distribution by survival](https://github.com/user-attachments/assets/fb4cec55-7bf6-460f-a663-caeb75bea07b)


###  > Grouped Survival Rates (Categorical)

#### By Sex
- Females had much higher survival rates.
- ![Survival Rate by sex](https://github.com/user-attachments/assets/03b681db-af5c-42b7-9fdd-acda2cd3f516)


#### By Pclass
- 1st class passengers survived more.
- 3rd class had the lowest survival.
- ![Survival rate by passenger calss](https://github.com/user-attachments/assets/d131574e-ead2-4651-849d-a48d07a0fd34)


#### By Embarked
- Port 'C' (Cherbourg) had the best survival outcomes.
- Most people embarked from 'S', but survival was lower there.
- ![Survival rate by embarked port](https://github.com/user-attachments/assets/9b3d1437-695f-45f5-9586-7f96fd334b41)


#### By Family Size
- Passengers with 3–4 family members had the highest survival rate.
- Large families and solo travelers had worse outcomes.
- ![Survival Rate by family size](https://github.com/user-attachments/assets/cc3453d5-df1a-42a0-b766-8b382373961b)


#### By Title
- Miss, Mrs, and Master had better survival rates.
- Rare titles (military or nobility) had poor survival rates.
- ![survival rate by Title](https://github.com/user-attachments/assets/ddca481f-6c29-4e45-9822-62ec9dc10e86)


###  > Feature Relationships

#### Correlation Heatmap
- Fare positively correlated with survival.
- Pclass negatively correlated (as class increases numerically, survival drops).
- FamilySize has low but slightly negative correlation.
- ![Correlation Matrix](https://github.com/user-attachments/assets/6bbd2e07-f10e-402c-b835-8caf20b88c64)


#### Pairplot
- Shows separability in Fare and Age between survivors and non-survivors.
- Highlights potential feature importance for modeling.
- ![Pairplot of Numeric Features by Survival](https://github.com/user-attachments/assets/9e24668b-ffc2-44cc-a505-af223d622d9c)


---

##-----------------------------------------Key Insights, Patterns & Anomalies-------------------------------------

###  Insights
- Females, younger passengers, and 1st class travelers had the highest survival.
- Fare and Title are important indicators of social class, which impacted survival.

###  Patterns
- Strong survival pattern by sex and class.
- Medium-sized families (3–4 members) had better outcomes.
- Passengers who embarked at Cherbourg survived more often.

###  Anomalies
- Fare distribution has major outliers.
- Some passengers with high fares still did not survive — possible anomalies.
- A few solo travelers survived despite low survival odds.

---

##  Summary Table

| Feature     | Insight |
|-------------|---------|
| Sex         | Strongest indicator of survival; females prioritized |
| Pclass      | 1st class passengers had best survival chances |
| Age         | Children and young adults more likely to survive |
| Fare        | Higher fare correlates with better outcomes |
| FamilySize  | Medium-sized families had the best odds |
| Embarked    | Port 'C' had best survival rates |
| Title       | Social class and gender reflected in title influenced survival |

---

##  Conclusion

This analysis helps identify meaningful features for predictive modeling. It also highlights the importance of class, gender, and family size in survival outcomes.

