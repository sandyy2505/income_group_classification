# income_group_classification
Income group classification - Logistic Regression, AUC-ROC curve, confusion matrix

# Context 
DeltaSquare is an NGO that works with Government on matters of social policy to bring about a change in the lives of underprivileged sections of the society. They are tasked with coming up a policy framework by looking at the data govenment got from WHO. You as a data scientist at DeltaSquare are tasked with solving this problem and sharing a proposal for the government. 

# Objective

a) To find the most significant drivers of overall income of an invidividual
b) To build a prediction model that can help government target the right pockets of the society 

# Key Questions

1 - What are the different factors that influence income of an invdividual?
2 - Is there a good predictive model for income that exisits? What does the performance assessment look like for such a model?

# Dataset

The data contains characteristics of the people
* age: continuous - age of a Person 
* workclass: Where do a person works - categorical -Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
* fnlwgt:This weight is assigned by  Current Population Survey (CPS).People with similar demographic characteristics should have similar weights, since it is a feature aimed to allocate similar weights to people with similar demographic characteristics -  continuous 
* education: Degree the person has - Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
* education-num: no. of years a person studied - continuous.
* marital-status: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
* occupation: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
* relationship: Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
* race: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
* sex: Female, Male.
* capital-gain: Investment gain of the person other than salary - continuous
* capital-loss: Loss from investments - continuous
* hours-per-week: No. of hours a person works - continuous.
* native-country: United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.
* salary: >50K, <=50K (dependent variable, the salary is in Dollars per year)

# Selecting subset of important features using Sequential Feature Selector method
*Why we should do feature selection*
- Reduces dimensionality
- Discards uninformative features
- Discards deceptive features (Deceptive features appear to aid learning on the training set, but impair generalisation)
- Speeds training/testing

### How sequential feature selector works?
#### It starts with an empty model and adds in variables one by one.
* In each forward step, you add the one variable that gives the single best improvement to your model.

* Most overall significant varaibles  are  :
 - 'marital_status',
 - 'occupation', 
 -'relationship',
 - 'sex', 
 -'working_hours_per_week', 
 -'capital_gain', 
 -'capital_loss', 
 -'workclass'
 
 ### Conclusion
- The model with the best accuracy was one with no multicollinearity
- The most important significant variables are :
  - 'capital_gain': People who have obtained gain from an investment have a higher likelihood of salary above 50,000 dollar
  - 'capital_loss': People who have invested and have got loss also have a higher likelihood of getting a high income of above 50,000 dollar
  -'workclass_ Never-worked': People who have never worked have a very high likelihood of getting a salary below 50,000 dollar
  -'workclass_ Without-pay': People whose work-class is without-pay have a higher likelihood of having a salary below 50,000 dollar
  - 'education_ Doctorate': People who are having the education of doctors have a higher likelihood of having salary above 50,000 dollar
  - 'education_ Preschool': people who have been educated till preschool only have a higher likelihood of salary below 50,000 dollar
  - 'education_ Prof-school': People who are educated from Professional school have a higher likelihood of having a salary above 50,000 dollar
  - 'occupation_ Handlers-cleaners': people who have the occupation of handlers-cleaners have a higher likelihood of having a salary below 50,000 dollars. 
  -'race_ Asian-Pac-Islander': people of race Asia -pacific have a higher likelihood of having salary above 50,000 dollar
  - marital_status: People who are married have a higher likelihood of having a salary above 50,000 dollars.

* People with ethnicity-Asian, did doctorate or prof-school in education, are married and invest more are more likely to have a salary above 50,000 Dollars

# Recommendations
- The government should promote education among citizens, they should make policies for better higher education like a professional degree course or doctorate for citizens.
- The government should implement laws to ensure that people are paid fairly for their work
- The government should strengthen the facility for marriage institutions in the society so that people give more preference to living a married life that will lead to a higher salary
