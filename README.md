# Global Terrorism Data Analysis
### Machine Learning, Statistical Modeling & Geographic Patterns in R

An exploratory and predictive analysis of more than 200,000 historical terrorism incidents using statistical learning, classification algorithms, and geographic clustering.

**Technologies:** R · Tidyverse · ggplot2 · caret · Random Forest · XGBoost · Logistic Regression · K-Means Clustering

---

## Project Overview

The Global Terrorism Database (GTD) contains detailed information about terrorist incidents worldwide, including their geographic locations, attack characteristics, and recorded outcomes.

This project examines historical patterns in terrorist activity while exploring how different machine learning algorithms perform when applied to large, imbalanced datasets.

Using **209,706 observations spanning 1970–2020**, I investigated geographic distributions, evaluated classification methods, and explored how class imbalance affects predictive performance.

A central finding was that **high classification accuracy does not necessarily indicate a useful model**, particularly when one outcome occurs much more frequently than another.

## Research Questions

This analysis was designed to explore four questions:

1. Can machine learning models classify recorded attack outcomes using historical event characteristics?
2. How does class imbalance influence model performance?
3. How do different classification algorithms compare?
4. What geographic patterns emerge from unsupervised clustering?

## Dataset

**Source:** [Global Terrorism Database (GTD)](https://www.start.umd.edu/gtd)

The original dataset contains:

| Characteristic | Description |
|---|---|
| Observations | 209,706 |
| Original variables | 135 |
| Analysis variables | 45 |
| Time period | 1970–2020 |
| Geographic coverage | Worldwide |
| Primary classification target | Recorded attack success |

The analysis includes geographic coordinates, regional classifications, attack characteristics, and other recorded event attributes.

The dataset presents several challenges common in real-world analytics, including missing values, categorical variables, extreme observations, and class imbalance.

**Data access:** The GTD is maintained by the University of Maryland's START consortium. Refer to the [official GTD website](https://www.start.umd.edu/gtd) for access and applicable usage restrictions.

## Methodology

The project combines exploratory data analysis, supervised learning, and unsupervised clustering.

### 1. Exploratory Data Analysis

I examined the structure and distribution of the dataset using R, including:

- Summary statistics and missing-value patterns
- Correlation analysis and variable selection
- Geographic distributions of recorded incidents
- Regional differences in incident frequency
- Distribution of successful and unsuccessful attacks

Visualizations were created using **ggplot2** and **ggcorrplot**.

### 2. Supervised Machine Learning

Four classification approaches were evaluated:

**Logistic Regression**

Used as an interpretable baseline for binary classification.

**Random Forest**

An ensemble learning approach used to model relationships between event characteristics and recorded outcomes.

**Balanced Random Forest**

A Random Forest approach incorporating up-sampling to address the underrepresentation of the minority class.

**XGBoost**

A gradient-boosted decision tree model used to explore an additional ensemble learning approach.

### 3. Unsupervised Learning

**K-Means Clustering** was applied to geographic coordinates to explore spatial groupings of historical incidents.

The analysis included geographic cluster visualizations, an elbow plot, and comparisons between generated clusters and predefined geographic regions.

## Results and Findings

The original analysis highlighted the challenges of evaluating classification models on imbalanced datasets.

### Classification Performance

| Model | Reported Accuracy | Reported Minority-Class Recall |
|---|---:|---:|
| Logistic Regression | 88.35% | 0% |
| Random Forest | 89.14% | 10.5% |
| Balanced Random Forest | 82.95% | 42.1% |
| XGBoost | 30.18% | Not reported here |

*These figures reflect the original academic analysis and have not been independently revalidated. The XGBoost result requires verification before being used for model ranking.*

### Key Observations

**Accuracy alone can be misleading.**

The logistic regression model achieved 88.35% accuracy but failed to identify the minority class. This demonstrated why overall accuracy should not be the only metric used to evaluate classification performance.

**Class balancing changes the performance trade-off.**

The balanced Random Forest model achieved lower overall accuracy than the original Random Forest but substantially higher reported minority-class recall.

**Model complexity does not guarantee better performance.**

The comparison illustrated that different algorithms and imbalance-handling strategies can produce substantially different results.

**Geographic clustering reveals spatial groupings.**

K-Means clustering produced geographic groupings that partially aligned with established regions, illustrating how unsupervised methods organize observations using location information.

## Project Files

| File | Description |
|---|---|
| [R Markdown Analysis](Project/Report_McCullough.Rmd) | Source code, methodology, visualizations, and analysis |
| [HTML Report](Project/Report_McCullough.html) | Rendered analysis report |
| [Project Presentation](Presentation/Presentation_McCullough.pptx) | Presentation summarizing the project |
| [Original Proposal](Proposal/Proposal_Idea.pdf) | Initial research proposal |

## Tools and Technologies

| Technology | Application |
|---|---|
| R | Data processing, statistical analysis, and modeling |
| Tidyverse / dplyr | Data manipulation and exploration |
| ggplot2 / ggcorrplot | Data visualization |
| caret | Classification training and evaluation |
| randomForest | Ensemble classification |
| XGBoost | Gradient-boosted classification |
| glmnet | Regularized regression tools |
| R Markdown | Reproducible analytical reporting |

## Challenges and Lessons Learned

Working with a large historical dataset introduced several practical challenges.

**Class imbalance:** The strong difference in class frequencies demonstrated how misleading accuracy can become when models primarily predict the majority outcome.

**Missing data:** The dataset required careful consideration of incomplete observations and placeholder values.

**Computational requirements:** Training ensemble models on a large dataset required managing execution time and saving fitted models for reuse.

**Interpretability:** Geographic clustering required distinguishing mathematical groupings from actual geographic or political boundaries.

This project strengthened my experience with exploratory analysis, machine learning workflows, model comparison, and communicating statistical findings.

## Limitations

This analysis is exploratory and should not be interpreted as a tool for predicting specific future incidents.

The dataset reflects historical reporting and may contain incomplete records, reporting biases, and measurement limitations.

Additionally, geographic associations do not establish causal relationships, and classification performance depends on the available features, modeling decisions, and evaluation procedures.

## About the Author

**Katelyn McCullough**

B.S. Data Science | Florida Polytechnic University

Interested in data science, machine learning, data engineering, and applying statistical methods to complex real-world problems.

- **Portfolio:** [Katelyn Codes](https://katelynmccullough.github.io/katelyncodes/)
- **GitHub:** [katelynmccullough](https://github.com/katelynmccullough)
- **LinkedIn:** [Katelyn McCullough](https://www.linkedin.com/in/katelynmccullough09/)

---

*This project was originally developed as an academic statistical learning project and is presented as part of my data science portfolio.*

**Data source:** National Consortium for the Study of Terrorism and Responses to Terrorism (START), University of Maryland. Global Terrorism Database.