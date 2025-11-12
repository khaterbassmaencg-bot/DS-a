
NOM : KHATER / PRENOM: BASSMA / GROUPE : S7 CAC2 / Module : DATA SIENCE

Dataset Information:this database contains 76 attributes, but all published experiments refer to using a subset of 14 of them.  In particular, the Cleveland database is the only one that has been used by ML researchers to date.  The "goal" field refers to the presence of heart disease in the patient.  It is integer valued from 0 (no presence) to 4. Experiments with the Cleveland database have concentrated on simply attempting to distinguish presence (values 1,2,3,4) from absence (value 0).  
   
The names and social security numbers of the patients were recently removed from the database, replaced with dummy values.

One file has been "processed", that one containing the Cleveland database.  All four unprocessed files also exist in this directory.

To see Test Costs (donated by Peter Turney), please see the folder "Costs" 
Creators
Andras Janosi

William Steinbrunn

Matthias Pfisterer

Robert Detrano
<img src="ghraphique 1.png" style="height:1000px;margin-right:1000px"/>
<img src="ghraphe 2.png" style="height:1000px;margin-right:1000px"/>
<img src="ghraphe 3.png" style="height:1000px;margin-right:1000px"/>
<img src="ghraphe 4.png" style="height:1000px;margin-right:1000px"/>
<img src="ghraphe 5.png" style="height:1000px;margin-right:1000px"/>
<img src="ghraphique 6.png" style="height:1000px;margin-right:1000px"/>
Data Analysis Key Findings
Age Distribution: The age distribution is somewhat normal, primarily centered around individuals in their 50s and 60s, suggesting a higher prevalence of heart disease in middle-aged to older populations within the dataset.
Resting Blood Pressure (trestbps): The distribution is right-skewed, with most values concentrated between 120-140 mmHg, indicating that the majority of individuals have blood pressure in this range, with fewer having very high readings.
Cholesterol (chol): Cholesterol levels also exhibit a right-skewed distribution, with a significant portion of values falling between 200-250 mg/dl, and some individuals presenting much higher levels.
Maximum Heart Rate Achieved (thalach): This feature displays a left-skewed distribution, peaking in the 150-170 bpm range, suggesting that many patients in the study achieve higher heart rates during exercise.
ST Depression (oldpeak): The oldpeak distribution is heavily concentrated at lower values (0-2), indicating that many patients have minimal or no ST depression.
Gender Imbalance: The dataset contains significantly more males (approximately 200) than females (approximately 100), which could impact the generalizability of gender-specific findings.
Chest Pain Type (cp): Asymptomatic chest pain (Type 4) is the most prevalent type among patients, followed by non-anginal pain (Type 3).
Fasting Blood Sugar (fbs): A vast majority of patients (over 250) have fasting blood sugar less than or equal to 120 mg/dl (coded as 0).
Number of Major Vessels (ca): Most patients have 0 major vessels colored by fluoroscopy, with counts decreasing as the number of vessels increases. Missing values in ca and thal were present but handled during plotting.
Target Variable Distribution (num): The target variable, indicating heart disease diagnosis, shows a severe class imbalance, with a high majority of observations falling into category 0 (no heart disease or < 50% diameter narrowing). The counts for categories 1, 2, 3, and 4 are considerably lower and decrease with increasing severity.
Insights or Next Steps
The significant class imbalance in the target variable (num) suggests that specific techniques for imbalanced datasets, such as oversampling, undersampling, or using appropriate evaluation metrics (e.g., F1-score, precision, recall) might be necessary for model training to avoid bias towards the majority class.
The presence of skewed distributions in numerical features like trestbps, chol, and thalach might require data transformation techniques (e.g., logarithmic transformation, standardization) before applying certain machine learning algorithms that assume normal distributions.
