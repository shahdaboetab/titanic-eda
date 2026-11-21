# Titanic Survival: Exploratory Data Analysis

Exploratory data analysis of the Titanic passenger dataset (891 passengers) using Python. The notebook cleans the data, builds group-based summaries and visualizes what separated survivors from non-survivors.

Built for the **Elevvo Data Analytics Internship** (Task 2, Level 1).

## Business question

Which passenger characteristics (gender, class, age, family size, port of embarkation) were most associated with survival?

## Dataset

- **Source:** Titanic training dataset (`titanic.csv`), 891 rows and 12 columns. Loaded directly from a public GitHub URL, so no local file is needed.
- **Key columns:** `Survived`, `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Embarked`.

## Approach

1. **Inspection:** shape, data types, summary statistics, missing values and duplicates.
2. **Cleaning:**
   - `Age` (about 20% missing): filled with the median.
   - `Embarked` (2 missing): filled with the mode.
   - `Cabin` (about 77% missing): dropped.
   - No duplicate rows were found.
   - `Sex`, `Pclass` and `Embarked` converted to categorical types.
3. **Feature engineering:** `FamilySize`, `IsAlone`, `AgeGroup`.
4. **Analysis:** survival rate by gender, class, gender and class together, port, age group and family size.
5. **Visualization:** bar plots, an age distribution plot and a correlation heatmap.

## Key findings

| Pattern | Result |
|---|---|
| Overall survival | **38.4%** |
| Gender | Women **74.2%** vs. men **18.9%** |
| Passenger class | 1st **63.0%**, 2nd **47.3%**, 3rd **24.2%** |
| Gender x class | 1st class women **96.8%**; 3rd class men only **13.5%** |
| Age group | Children (12 and under) **58.0%**; seniors **22.7%** (only 22 passengers) |
| Family size | 2 to 4 members: **55% to 72%**; travelling alone: **30.4%** |
| Port | Cherbourg highest (**55.4%**), likely because it had more 1st class passengers |
| Correlations | `Survived` with `Fare` **+0.26** and `Pclass` **-0.34**; `Pclass` with `Fare` **-0.55** |

Gender and class together explain most of the difference: being a woman in 1st or 2nd class almost guaranteed survival, while 3rd class men had the lowest chances.

## Limitations

- About 20% of ages were imputed with the median, which can slightly flatten age effects.
- The analysis is observational. These patterns show association, not causation.
- Some groups are small (for example, seniors and very large families), so their percentages are less reliable.

## How to run

1. Open `Titanic_EDA.ipynb` in Google Colab or Jupyter Notebook.
2. Run all cells from top to bottom. The dataset downloads automatically.

**Requirements:** Python 3, pandas, numpy, matplotlib, seaborn.

## Repository contents

| File | Description |
|---|---|
| `Titanic_EDA.ipynb` | Full analysis with outputs and charts |
| `README.md` | Project summary |

## Author

**Shahd Ashraf Aboetab**
[GitHub](https://github.com/shahdaboetab) | [LinkedIn](https://linkedin.com/in/shahdaboetab)
