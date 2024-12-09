# MBP1201H-Biostatistics
Final project for graduate level biostatistics course. Applying biostatistical methods to answer research hypotheses based on a heart disease dataset.

I will be utilizing a dataset with Heart Disease information from UCI (available at https://archive.ics.uci.edu/dataset/45/heart+disease). This dataset was originally compiled from studies conducted between 1988 and the early 1990s and represents a combination of four databases with data collected from the following locations:

1.	Cleveland Clinic Foundation (Cleveland, Ohio, USA)
2.	Hungarian Institute of Cardiology (Budapest, Hungary)
3.	V.A. Medical Center (Long Beach, California, USA)
4.	University Hospital (Zurich, Switzerland)

While the full dataset contains 76 attributes, only 14 of these have been used in research studies. These 14 attributes were chosen for their clinical relevance and widespread use in previous experiments. The Cleveland database is the only one that has been extensively used by machine learning researchers and is also the focus of this project. The file, `processed.cleveland.data`, contains the Cleveland database, with attributes formatted for research purposes. The data was collected to assess factors contributing to heart disease and evaluate diagnostic models.

## **Hypothesis 1: Is there a significant difference in ST Depression Induced by Exercise (oldpeak) in Males vs Females?**

The ST segment is the portion of an electrocardiogram (ECG) tracing between the end of the “S” wave and the start of the “T” wave (https://www.medicalnewstoday.com/articles/st-segment-depression). In healthy individuals, this segment appears near the baseline. However, a depressed or elevated ST segment can indicate underlying cardiovascular conditions, such as myocardial ischemia or coronary artery disease. This dataset includes the degree of ST depression induced by exercise (referred to as “oldpeak”), a measurable indicator of stress-induced changes in cardiac function.

Sex-specific differences are well-documented in heart disease presentation, risk factors, and physiological responses to exercise. Investigating whether males and females differ significantly in ST depression levels during exercise can provide insights into how heart disease manifests differently between sexes and potentially inform tailored diagnostic approaches. This hypothesis is measurable and realistic, aligning with existing knowledge of cardiovascular physiology.

Variables Involved:
- Dependent Variable: ST Depression Induced by Exercise (oldpeak) (Numerical, Continuous)
- Independent Variable: Sex (Categorical, Binary: 0 = Female, 1 = Male)

Statistical Method:
- A two-sample t-test / Mann-Whitney U test (if assumptions of normality are not met) will be used to compare the distributions of oldpeak between males and females.
- Null Hypothesis: There is no significant difference in ST Depression Induced by Exercise (oldpeak) between males and females.
- Alternative Hypothesis: There is a significant difference in ST Depression Induced by Exercise (oldpeak) between males and females.

## **Hypothesis 2: Can age and serum cholesterol predict the presence of heart disease?**

Age is already a well established risk factor heart disease. Older age is known to be associated with increased risk factors for heart disease making it a suitable metric for a classification problem. Serum cholesterol tends to be a risk factor for atherosclerosis which commonly leads to heart disease, also making it a suitable metric for a classification problem. This hypothesis aims to evaluate whether age and serum cholesterol levels are good predictors for the presence of heart disease.

Variables Involved:
- Dependent Variable: Heart Disease Presence (target) (Categorical, Binary: 0 = No Heart Disease, 1 = Heart Disease Present)
- Independent Variables: Age (Numerical, Continuous), Serum Cholesterol (Numerical, Continuous)

Statistical Method:
- A logistic regression classification model will be used to assess whether age and serum cholesterol can predict the likelihood of heart disease. We will utilize the AUC-ROC value to evaluate the model’s performance, where a higher AUC indicates better discriminatory ability to distinguish between individuals with and without heart disease.
