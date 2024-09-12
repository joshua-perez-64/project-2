# project-2

Your presentation should cover the following:
An executive summary or overview of the project and project goals. (5 points)
An overview of the data collection, cleanup, and exploration processes. (5 points)
The approach that your group took in achieving the project goals. (5 points)
Any additional questions that surfaced, what your group might research next if more time was available, or share a plan for future development. (3 points)
The results and conclusions of the application or analysis. (3 points)
Slides effectively demonstrate the project. (2 points)
Slides are visually clean and professional. (2 points)

Objective: Screen pre-diabetes/diabetes outcomes using various health indicators.
Significance: Understanding diabetes risk factors and enabling early detection
Goals: Develop a predictive model to screen patients and predict their risk of pre-diabetes/diabetes

# Project Objective

The objective of this project was to come up with an AI model that can screen pre-diabetes/diabetes using multiple health risk factors. As a result, we developed a logistic regression AI model with 73% accuracy and a recall of 77% to predict diabetes.

---

# Data Collection and Initial Analysis

Initially, we started off by searching for datasets. We found a dataset from the UC Irvine Machine Learning Repository called the [CDC Diabetes Health Indicators dataset](https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators). This dataset can also be found on Kaggle and is part of the Behavioral Risk Factor Surveillance System, which is a health-related telephone survey conducted annually by the CDC.

This dataset was chosen because it had approximately 215,000 instances, whereas other health datasets had less data.

---

### Feature Selection and Data Flaws

The data was analyzed, and we focused on which features felt relevant for our model. We removed the features "income" and "healthcare coverage" because we wanted to select features not strongly tied to financial outcomes. Additionally, our app aimed to consider audiences without high income or health coverage. Those with health coverage were more likely to get risk assessments from their doctors.

Using clinical judgment and domain expertise, we determined that even though income and healthcare coverage could be relevant, they were not as impactful as other lifestyle features. After finalizing the features, we looked at the number of pre-diabetic/diabetic versus non-diabetic instances in the data:

- **Non-diabetic cases:** 218,334
- **Pre-diabetic/diabetic cases:** 35,346

This indicated a class imbalance between diseased and non-diseased individuals. We also observed that many of the features were already encoded into buckets, while BMI was the only feature with quantitative values. The remaining features were qualitative and encoded into numbers.

---

# Model Selection and Evaluation

After cleaning and exploring the data, we proceeded with model development. We selected the following models:

- **Logistic Regression**
- **Random Forest**
- **Decision Tree**

---

### Model Rationale

We felt that the **Logistic Regression** might be a good fit because the outcome was a simple "yes" or "no" answer, determining whether the patient was at risk for diabetes. Most of our features were encoded, leading to binary "yes/no" answers.

Additionally, since our data was simple and complete, we considered **logistic regression** a strong candidate for hypothesis testing. **Random forest** was chosen because it handles multiple complex features better.

Although we did not expect the **decision tree** to be the best model, we included it for comparison purposes.

---

### Initial Results

When we built each model, the accuracy results were:

- **Logistic Regression:** 86% accuracy
- **Random Forest:** 85% accuracy
- **Decision Tree:** 80% accuracy

While these results seemed promising, we realized that our models were better at predicting non-diabetic cases due to the class imbalance. This led to poor performance in detecting diabetic patients. Upon further investigation of precision and recall, both values were low for all three models.

---

# Model Optimization

To address the issue of class imbalance and improve the model, we applied the following techniques:

1. Reducing the number of features
2. Resampling techniques (under/oversampling)
3. Scaling the data

---

# Final Model and Results

Our most successful model was the **logistic regression model** using undersampling to balance the data between diabetics and non-diabetics. We also reduced outliers in the BMI feature.

This model showed the highest accuracy at 73%. Upon further analysis of the confusion matrix, the recall for diabetic cases was 77%. We prioritized recall because, as a diabetes risk assessment tool, it is crucial not to miss diabetic cases.

In other words, we preferred fewer **false negatives** (missing diabetic cases) over more **false positives** (incorrectly identifying non-diabetics as diabetics). This approach is more beneficial as it encourages patients to get checked, reducing the risk of missed diagnoses.

---

# Future Implications

For future improvements, we would:

1. **Expand the dataset** by collecting more diabetic cases from diverse populations, which would help balance the data.
2. **Global expansion** of the dataset to get a broader, more diverse sample for model training.
3. **Explore advanced data models**, such as deep neural networks, to better handle complex data.
4. **Include additional features** in the dataset for a more holistic view of health risks.
5. **Granular classification** into Type 1, Type 2, and pre-diabetic cases, to improve disease risk prediction.
6. **Develop a risk assessment application** that would flag users for potential diabetes risk and encourage them to seek medical advice.

---

# Job Market Analysis

The disease burden of diabetes in the US is approximately 38.4 million people across all ages. As the population continues to age, diabetes is expected to become even more prevalent in the future. According to **Dr. Rowley from the NIH**, diabetes cases are projected to increase to **55 million by 2030**. This highlights the urgent need to address the growing disease burden.

Jobs in healthcare management are anticipated to grow by around **28% from 2021 to 2031**, reflecting the increasing demand for professionals in this sector. The cost of addressing this issue, depending on the scope and region, can range from **$75,000 to $300,000**. This estimate is based on grants typically awarded by universities (around **$50,000**), and includes costs for public health researchers and incorporating global healthcare opinions from doctors and experts.

---

# Citations
    Teboul, Alex. “Diabetes Health Indicators Dataset.” Kaggle, 8 Nov. 2021, www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset.

    Health Care Job Growth Remains Strong through 2031, www.purdueglobal.edu/blog/health-sciences/growing-health-care-workforce/. Accessed 12 Sept. 2024. 

    Rowley, William R, et al. “Diabetes 2030: Insights from Yesterday, Today, and Future Trends.” Population Health Management, U.S. National Library of Medicine, Feb. 2017, www.ncbi.nlm.nih.gov/pmc/articles/PMC5278808/.

    “About the Special Diabetes Program - NIDDK.” National Institute of Diabetes and Digestive and Kidney Diseases, U.S. Department of Health and Human Services, www.niddk.nih.gov/about-niddk/research-areas/diabetes/type-1-diabetes-special-statutory-funding-program/about-special-diabetes-program. Accessed 11 Sept. 2024. 

    “National Diabetes Statistics Report.” Centers for Disease Control and Prevention, Centers for Disease Control and Prevention, www.cdc.gov/diabetes/php/data-research/index.html. Accessed 11 Sept. 2024.

    Ceriello, Antonio, and Francesco Prattichizzo. “Variability of Risk Factors and Diabetes Complications.” Cardiovascular Diabetology, U.S. National Library of Medicine, pubmed.ncbi.nlm.nih.gov/33962641/. Accessed 9 Sept. 2024. 

    “Lesson 4: Diabetes Risk Factors (English).” Edited by Care New England, YouTube, YouTube, 20 Oct. 2020, www.youtube.com/watch?v=rrX2Hn2iesM. 

    “Type 2 Diabetes.” Mayo Clinic, Mayo Foundation for Medical Education and Research, 14 Mar. 2023, www.mayoclinic.org/diseases-conditions/type-2-diabetes/symptoms-causes/syc-20351193. 

    “Diabetes Risk Factors.” Centers for Disease Control and Prevention, Centers for Disease Control and Prevention, www.cdc.gov/diabetes/risk-factors/index.html. Accessed 9 Sept. 2024.

    ND, Wong ND, and Sattar N. “Cardiovascular Risk in Diabetes Mellitus: Epidemiology, Assessment and Prevention.” Nature Reviews. Cardiology, U.S. National Library of Medicine, pubmed.ncbi.nlm.nih.gov/37193856/. Accessed 9 Sept. 2024.

    “Accuracy vs. Precision vs. Recall in Machine Learning: What’s the Difference?” Evidently AI - Open-Source ML Monitoring and Observability, www.evidentlyai.com/classification-metrics/accuracy-precision-recall. Accessed 9 Sept. 2024. 
