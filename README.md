# 🚢 Titanic Survival Analysis: EDA & Data Cleaning Project

![Titanic](https://upload.wikimedia.org/wikipedia/commons/f/fd/RMS_Titanic_3.jpg)

## 📌 Objective
Analyze the Titanic dataset to uncover the key factors influencing passenger survival using data cleaning, feature engineering, and exploratory data analysis (EDA).

---

## 📊 Dataset

- **Source:** Seaborn's built-in Titanic dataset  
- **Size:** 891 rows × 15 columns  
- **Description:** Includes demographic data, ticket info, travel class, and survival status.

---

## 🧰 Tools & Libraries

- Python  
- Pandas  
- NumPy  
- Seaborn  
- Matplotlib  
- Scikit-learn

---

## 🧪 Steps Performed

### 1. Environment Setup
- Installed required Python packages.
- Loaded the dataset from Seaborn.

### 2. Initial Data Exploration
- Used `.head()`, `.info()`, `.describe()`, and `.isnull().sum()` to understand the structure and quality of the data.
- Identified missing values in `age`, `embarked`, `deck`, and `embark_town`.

### 3. Data Cleaning
- **Missing Values:**
  - Filled `age` with the median.
  - Filled `embarked` with mode.
  - Filled `deck` with `'Unknown'`.
- **Data Type Corrections:**
  - Converted `pclass`, `sex`, and `embarked` to `category`.

### 4. Feature Engineering
- Created new features:
  - `family_size = sibsp + parch + 1`
  - `is_alone = 1 if family_size == 1 else 0`
  - `age_group` using `pd.cut` (Child, Teen, Young Adult, Adult, Senior)

### 5. Exploratory Data Analysis (EDA)

- **Survival Rate by Gender:**  
  - Females had a much higher survival rate than males.
  
- **Survival Rate by Passenger Class:**  
  - First class passengers had significantly higher survival rates.
  
- **Gender + Class Survival Interaction:**  
  - Third class males had lowest survival, while first class females had highest.
  
- **Survival Rate by Age Group:**  
  - Children and seniors had better survival odds.
  
- **Survival by Family Size:**  
  - Families of 3–4 had the best survival rate.
  
- **Embarkation Port Analysis:**  
  - Passengers from Cherbourg had higher survival rates.
  
- **Siblings/Spouses Aboard (`sibsp`):**  
  - Traveling with 1–2 family members increased survival odds.
  
- **Parents/Children Aboard (`parch`):**  
  - Moderate family groups fared better than lone travelers.
  
- **Fare vs Class & Survival:**  
  - Higher fares and 1st class = higher survival.

---

## 📈 Correlation Analysis

- Categorical variables were encoded.
- A heatmap of the correlation matrix revealed:
  - `sex`, `pclass`, and `fare` strongly correlated with `survived`.
  - `is_alone` and `family_size` showed weak negative correlation.

---

## 🔍 Multivariate Relationships

- Created a `pairplot` of `age`, `fare`, and `family_size`:
  - Survivors: Young, paid high fare, and had medium family size.
  - Non-survivors: More spread, especially alone or with large families.

---

## 📌 Key Takeaways

- **Gender and Class** are the strongest predictors of survival.
- Family size, age, and fare also contribute to survival chances.
- Combining visualizations with feature engineering gives deep insight.

