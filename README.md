# Heart Failure Prediction

## Problem Definition:
Given clinical parameters about a patient, can we predict whether or not they have heart disease? 

## Introduction:
Cardiovascular diseases (CVDs) fall among the top cause of death globally, that is approximately 31% of all deaths worldwide. Highest CVDs deaths are due to strokes and heart attack. A significant fraction of this takes place for people under the age of 70 years. It is thus important to monitor different hearth health related parameters. A meaningful data set on this therefore be valuable toward early prediction of CVDs.

## Dataset:
Heart Failure Prediction Dataset from Kaggle [https://www.kaggle.com/fedesoriano/heart-failure-prediction](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) from kaggle. 
The dataset contains 12 columns and 918 observations(Rows)
Among 12, 11 of the columns are medical parameters and a Target variable, i.e., ‘HeartDisease’.

## Data dictionary:

1.   age - age in years
2.   sex - (M = male; F = female)
3.   ChestPainType  - chest pain type

    TA:   Typical angina: chest pain related decrease blood supply to the heart

    ATA:   Atypical angina: chest pain not related to heart

    NAP:   Non-anginal pain: typically esophageal spasms (non heart related)
    
    ASY:   Asymptomatic: chest pain not showing signs of disease


4.  RestingBP - resting blood pressure (in mm Hg on admission to the hospital) anything above 130-140 is typically cause for concern
5.  Cholesterol - serum cholesterol in mg/dl
serum = LDL + HDL + .2 * triglycerides
above 200 is cause for concern
6.  FastingBS  - (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
'>126' mg/dL signals diabetes
7.  RestingECG  - resting electrocardiographic results

  Normal: Nothing to note

  ST: ST-T Wave abnormality can range from mild symptoms to severe problems
signals non-normal heart beat.

  LVH: Possible or definite left ventricular hypertrophy Enlarged heart's main pumping chamber
8.  MaxHR - maximum heart rate achieved
9.  ExerciseAngina - exercise induced angina (Y = yes; N = no)
10.  Oldpeak - ST depression induced by exercise relative to rest looks at stress of heart during excercise unhealthy heart will stress more
11.  ST_Slope  - the slope of the peak exercise ST segment

  Up: Upsloping: better heart rate with excercise (uncommon)

  Flat: Flatsloping: minimal change (typical healthy heart)

  Down: Downslopins: signs of unhealthy heart
12.  HeartDisease  - have disease or not (1=yes, 0=no) (= the predicted attribute or Target)

## Methodology:
1. Cleaning the data (handliing missing data, outliers etc)
2. Data visualisations techniques and statistical tests to evaluate the difference between the distribution of variables. 
Histograms, scatter plots to highlight the distinguishing features for disease prediction. 
3. Conduct a t-test to understand the statistical significance difference between the means of continuous parameters with the target classes.

## Data exploration:
The variables are categorised based on their type (categorical or continuous). Their distributions are studied. 

### Dependance of Heart disease on Gender: 
![image](https://user-images.githubusercontent.com/81338075/170843216-821de3f0-acda-42e2-81d9-7abe909b5898.png)
### Dependance of Heart disease on Chest pain type: 
![image](https://user-images.githubusercontent.com/81338075/170843245-241cd0c1-c216-44ed-896f-10c8acb4d896.png)
### Dependance of Heart disease on Fasting Blood Sugar: 
![image](https://user-images.githubusercontent.com/81338075/170843260-968a80d5-f67b-4bd4-902f-bf4c931f7ce7.png)
### Dependance of Heart disease on Resting ECG: 
![image](https://user-images.githubusercontent.com/81338075/170843279-b76a478c-4f9d-488e-8881-f62c7ad834b2.png)
### Dependance of Heart disease on Exercise Angina: 
![image](https://user-images.githubusercontent.com/81338075/170843289-4aa0bbdd-731d-40eb-88c6-bbaee6d5ab49.png)
### Dependance of Heart disease on ST Slope: 
![image](https://user-images.githubusercontent.com/81338075/170843306-9e6fc283-9393-459c-bf72-55c461876389.png)

### Dependanceof Heart disease on Continuous Variables like 'Age', 'RestingBP', 'Cholesterol', 'MaxHR', 'Oldpeak'
![image](https://user-images.githubusercontent.com/81338075/170843318-0abda67b-02a1-4065-b206-fda15a00cc1d.png)

1.   Age shows normal distribution. Heart Disease is seen higher on aged patients than young ones.
2.   RestingBP : resting blood pressure (in mm Hg on admission to the hospital) anything above 130-140 is typically cause for concern. Patients with Heart Disease have higher Resting BP.
3.   cholestorel {serum cholestoral in mg/dl} : above 200 is cause for concern.
4.   oldpeak ST depression induced by exercise relative to rest looks at stress of heart during excercise unhealthy heart will stress more

### Correlation of Age and Max Heart Rate with Target variable

![image](https://user-images.githubusercontent.com/81338075/170843369-cddc3bc0-3f29-48e2-bbb2-500f8188d8ac.png)

Heart disease are less seen in patients who are younger and have higher heartbeat compared to older with lower heartbeat.
## t-test and Statistical Analysis: 
### Dependance of Heart Disease on Age:
![image](https://user-images.githubusercontent.com/81338075/170843413-d5db5195-5929-4de5-af37-36494d713052.png)

Histograms and the statistical measures: 
* Negatively-skewed 
* Mean of age is higher for the patients with Heart Disease.

Null hypothesis: 
* Mean Age with heart disease = Mean Age without heart disease 
* The test statistic is 8.89 and the p-value is 3.007e-18. 
* Hence we can safely Reject the null hypothesis that means of those two are the same.

95% confidence interval:  
* 4.16 - 6.53 years higher for patients with heart disease.

### Dependance of Heart Disease on Resting Blood Pressure:
![image](https://user-images.githubusercontent.com/81338075/170843433-9e2201cf-10dd-4a4f-82ae-a4f8f47f62ee.png)

Histograms and the statistical measures:
* Negatively-skewed 
* Mean of RestingBP is higher for the patients with Heart Disease.


Null hypothesis: 
* Mean RestingBP with heart disease = Mean RestingBP without heart disease 
* The test statistic is 3.275 and the p-value is 0.001. 
* Hence we can safely Reject the null hypothesis that means of those two are the same.


95% confidence interval: 
* 1.65 - 6.35 higher for patients with Heart Disease.

### Dependance of Heart Disease on Cholesterol:
![image](https://user-images.githubusercontent.com/81338075/170843456-fc0d0e5e-fe24-4f6e-8c24-ec9d0f06ef36.png)
Plotting the histogram also led us to another benefit: spotting misleading values. The histogram has plotted some values of 0 cholesterol. This is a small selection of the data, so it is safe to simply drop it and proceed with the analysis.

![image](https://user-images.githubusercontent.com/81338075/170843493-8c3916e4-365e-4738-8488-5e39d6e975a0.png)

Histograms and the statistical measures:
* Positively-skewed. 
* Mean of Cholesterol is higher for the patients with Heart Disease.

Null hypothesis: 
* Mean Cholesterol with heart disease = Mean Cholesterol without heart disease 
* The test statistic is 2.848 and the p-value is 0.005. 
* Hence we can safely Reject the null hypothesis that means of those two are the same.

95% confidence interval: 
* 3.78 - 20.79 higher for patients with Heart Disease.

### Dependance of Heart Disease on Maximum Heart Rate
![image](https://user-images.githubusercontent.com/81338075/170843517-17236e06-0145-4aad-b7b4-2603b57a32a7.png)

Histograms and the statistical measures: 
* Normally distributed. 
* Mean of Maximum heart rate is lower among the patients with heart disease.

Null hypothesis: 
* Mean MaxHR with heart disease = Mean MaxHR without heart disease 
* The test statistic is -13.22 and the p-value is 1.137e-36. 
* Hence we can safely Reject the null hypothesis that means of those two are the same.
* 
95% confidence interval: 23.53 - 17.45 lower for patients with Heart Disease.

### Dependance of Heart Disease on Oldpeak
![image](https://user-images.githubusercontent.com/81338075/170843545-c3a0b094-ac61-4110-8663-08f3bc07fef9.png)

Histograms and the statistical measures:
* Positively-skewed
* Mean of Old peak is higher for the patients with Heart Disease.

Null hypothesis: 
* Mean Old peak with heart disease = Mean Old peak without heart disease 
* The test statistic is 13.36 and the p-value is 12.39e-37. 
* Hence we can safely Reject the null hypothesis that means of those two are the same.

95% confidence interval: 0.74 - 0.98 higher for patients with Heart Disease. 

## Conclusion: 
1. There are 55.34% patients have heart disease and rest 44.66% patients have no heart disease
2. Heart disease are mostly seen in male patients than female.
3. Patients with Asymptomatic(ASY) chest pain type have higher probability of having heart disease.
4. Nearly 80% of the patients with higher fasting blood sugar level have heart disease. Hence elevated fasting blood sugar level can hint the risk of CVD's.
5. Higher count of any type Resting ECG might indicate the heart disease.
6. Presence of Exercise induced Angina can be a strong indicator of CVD's.
7. Older patients with lower maximum heart rate are more prone to Heart disease than younger patients.
8. Paired-sample t-tests between the heart disease and variables like Age, Resting Blood Pressure, Cholesterol, Maximum heart rate, Old peak clearly rejects null hypothesis implying that they come from two different populations. Thus it hints that age, Resting Blood Pressure, Cholesterol, Maximum heart rate, Old peak are all important parameters in determining probability of heart diseases.





