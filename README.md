# Cardiovascular-risk-prediction-Almabetter
The given dataset contains the risk prediction of cardiovascular diseases where we have other parameters like age, education, sex, is_smoking, cigsperday, BPMeds, prevalent_stroke, prevalent_hyp, diabetes, totChol, sysBP, diaBP, BMI, heartrate, and glucose. Here TenYearCHD represents the risk prediction of cardiovascular diseases which is a target variable and remaining variables are considered as independent variables. First we perform univariate and bivariate analysis to analyse the relation among the independent variables. Correlation between target and independent variable is calculated, also with the help of heatmap we have selected features which are to be involved in model building. For these selected features we treat missing values, outliers, create new features from them, apply scaling and transformation techniques making them ready for model building. Finally we perform model building and check for the accurate evaluation metric score..
# Table of contents
* Data cleaning and manipulation
* Data Visualizations
* Feature Engineering
* Model implementation and feature importance
* Conclusion 
* Tools
# Data cleaning and manipulation 
Before data manipulation, the dataset has 3390 rows and 17 columns. We removed id column since it has as many number of unique values as number of rows. Therefore, it is not needed in the dataset while model building. Pulse pressure is calculated from sysBP and diaBP, as the information can be extracted from single variable instead of these two variables while model building. Now the new dataset has 3390 rows and 18 columns. 
# Data Visualizations
* TenYearCHD distribution
* Age and BMI distributions
* Sex and Education charts
* Is_smoking and CigsPerDay distribution
* Sys BP and diaBP distribution
* Prevalent stroke and prevalent hyp distribution
* Glucose and heartrate distribution
* Diabetes and BPMeds distribution
* Total cholesterol distribution
* TenYearCHD risk among different age groups
* Effect of smoking and number of cigarettes on having risk for CHD
* TenYearCHD risk patients having prevalent stroke
* TenYearCHD risk based on glucose measurement
* TenYearCHD risk based on patient's prevalent Hyper tension
* Effect of heartrate on CHD
* Effect of totChol on CHD
* Effect of sysBP and diaBP on CHD
* Pair Plot
* Correlation Heatmap
# Feature Engineering & Data Pre-processing
## Handling missing values
* There are missing values in Education, BPMeds, cigsPerDay, totChol, BMI, heartRate, and glucose. These missing values are imputed with either mode or median depending on the type of the variable. However, glucose had around 300 missing values so we used KNN imputer making sure that data is not biased.
## Multicollinearity  
* Distribution plots of all numerical variables including mean and median.
* From the Heatmap, we concluded that prevalentHYP and diabetes are correlated with pulse pressure and glucose respectively. The variables which have less correlation value are removed. Hence, prevalentHyp and diabetes are dropped from the dataset.
## Handling outliers
* From the boxplots, we notice that there are outliers in cigsPerDay, totChol, BMI, heartRate, glucose, and pulse_pressure. Using 95th and 5th percentile considering them as upper and lower limits of the variable, then we capped the points above upper limit and below lower limits with 95th and 5th percentiles respectively.
## Categorical encoding
* From the dataset, we see that sex, and is_smoking are the categorical variables. As there are more categories, instead of manually assigning integers, we used one hot coding and converted these columns to numerical variables.
## Feature Selection
* After all the feature engieering, age, education, cigsPerDay, BPMeds, prevalentStroke, totCHol, BMI, heartRate, glucose, pulse_pressure, and sex_M are selected as x variables.
## Handling data imbalance
* For treating data imbalance, we used SMOTE (Synthetic Minority Oversampling Technique) to balance the dataset. It works by randomnly picking point from the minority class and computing the k-nearest neighbors for this point, this way new points are generayted. As the data is important for us so we have opted for SMOTE.
# Model Implementation 
Now coming to the model implementation, following are the models used. 
* Decision tree
* Decision tree with hyperparameter tuning
* Logistic regression
* Logistic regression with hyperparameter tuning
* Random forest 
* Random forest with hyperparameter tuning
* KNN
* KNN with hyperparameter tuning
* SVM
* SVM with hyperparameter tuning
* Naive bayes
* Naive bayes with hyperparameter tuning
# Feature Importance
* From the feature importance plot, we see that age is the most important variable for TenYearCHD when decision tree model is used. Also, along with that pulse_pressure, totChol, cigsPerDay, heartRate, and Education when random forest is used. 
# Conclusion
## Conclusion from EDA
* After performing few analysis for the given dataset, it can be concluded that
* From the analysis, TenYearCHD column is plotted where there are very less people who are having the risk for cardiovascular diseases.
* Most of the records who has risk to CHD are in the age group between 38 to 68 in which maximum patients having CHD risk are of 63 years old followed by 52 years old.
* SysBP above 130 and diaBP above 80 can lead to a risk for CHD.
* Higher level of cholesterol can lead to a risk for CHD.
* 16% of patients had risk for CHD under smoking category whereas 13% of patients had risk under no smoking category. Therefore, smoking increased risk for CHD.
* It is observed that measure of glucose upto 80, no difference is seen whereas after 80 it seems like effecting to have risk for CHD.
## Conclusion from Model building
* In the dataset, there are missing values in Education, BPMeds, cigsPerDay, totChol, BMI, heartRate, and glucose.
* Education, and BPMeds variables are imputed with mode as they are categorical
* Median value is imputed for cigsPerDay, totChol, BMI, and heartRate
* For glucose we used KNN imputer as it had 304 missing values.
* In multicollinearity section, we finalised numerical columns with the help of correlation values from heatmap.
* Then we found outliers in cigsPerDay, totChol, BMI, heartRate, glucose, and pulse_pressure. Using 95th and 5th percentile considering them as upper and lower limits of the variable, then we capped the points above upper limit and below lower limits with 95th and 5th percentiles respectively.
* Then performed categorical encoding for sex and is_smoking.
* We selected age, education, cigsPerDay, BPMeds, prevalentStroke, totCHol, BMI, heartRate, glucose, pulse_pressure, and sex_M for model building.
* On comparing recall score and FN values of all the models, we concluded that decision tree with hyperparameter tuning gave us high recall score and less FN value.
# Tool
Google colab 
