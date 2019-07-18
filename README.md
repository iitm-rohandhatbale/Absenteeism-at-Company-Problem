# Absenteeism-at-Company-Problem
In this project we will find the Absenteeism of employees in the company using some Machine Learning Techniques.

## Data Description
01. ID (Individual Identification)
02. Reason for Absence ( Reasons 1-21 are registered in the international Classification od Diseases(ICD),Reasons 22-28 are not)
03. Date
04. Transportation Expenses
05. Distance to Work
06. Age
07. Daily work load avg (measuredin Min)
08. Body MAss Index
09. Education
10. Children
11. Pets
12. Absenteeism time in hr

### Reason for Absence
01. Certain Infectious and paeasitic diseases
02. Neoplasm
03. Diseases of blood and blood forming organ
04. Endocrine,nutritional and metabolic diseases
05. mental and behavioral diseases
06. Diseases of the nervious system
07. Diseases of the eye and adnexa
08. Diseases of the ear and masyoid process
09. Diseases of the circulatory system
10. Diseases of the respiratory system
11. Diseases of the digestive System
12. Diseases of the Skin
13. Diseases of the musculoskeletal system
14. Diseases of the genitourinary system
15. Pregnancy, childbirth and the puerperium
16. certain conditionsoriginating in perinatal period
17. Congenital malformation
18. Symtoms,Signs and abnormal clinical and laboratory findings not elsewhere classified
19. Injury,Poisoning
20. external causes of morbidity and mortality
21. Factors influencing health status and contact with health services
22. Patient follow-up
23. Medical consultation
24. Blood Donation
25. Laboratory Examination
26. Unjustified absence
27. Physiotherapy
28. Dental Consultation

## Data Preprocessing.

Reason for Absence is a categorical variable. So we should get dummies for these categorical Variable. 

reason_columns = pd.get_dummies(df['Reason for Absence']) will get the work done for us.

To avoid multicollinearity we will drop first column of 'reason_columns'.

Creating dummy variable of 28 categories and use them as it is is not very practicle. So we will group these 28 categories into 4 differebt categories .

* Reason_type_1 = resons 1-14
* Reason_type_2 = resons 15-17
* Reason_type_3 = resons 18-21
* Reason_type_4 = resons 22-28
