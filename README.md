
# **Executive Summary**

**This is UC Davis BAX452 Machine Learning Individual Project.**


The objective of the project is to **predict whether a person makes over 50K a year** given their demographic variations. To achieve this, several classification techniques are explored. In the end, random forest model yields to the best prediction result.

 * Source: https://archive.ics.uci.edu/ml/datasets/adult/


 * Income dataset is available at UCI machine learning website: http://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data

* Data dictionary is available at: https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.names

# **Data dictionary**


Extraction was done by Barry Becker from the 1994 Census database. A set of reasonably clean records was extracted using the following conditions: ((AAGE>16) && (AGI>100) && (AFNLWGT>1)&& (HRSWK>0))

##### *Listing of attributes*


**Target**
1. Predclass: >50K, <=50K.
  * Categorical, income Level is either higher or lower than $50K

**Categorical Attributes**

1. workclass: (categorical) Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
  * Individual work category
2. education: (categorical) Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
  * Individual's highest education degree
3. marital-status: (categorical) Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
  * Individual marital status
4. occupation: (categorical) Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
  * Individual's occupation
5. relationship: (categorical) Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
  * Individual's relation in a family
6. race: (categorical) White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
  * Race of Individual
7. sex: (categorical) Female, Male.
8. native-country: (categorical) United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.
  * Individual's native country

**Continuous Attributes**

1. age: continuous.
  * Age of an individual
2. education-num: number of education year, continuous.
  * Individual's year of receiving education
3. fnlwgt: final weight, continuous.
  * The weights on the CPS files are controlled to independent estimates of the civilian noninstitutional population of the US. These are prepared monthly for us by Population Division here at the Census Bureau.
4. capital-gain: continuous.
5. capital-loss: continuous.
6. hours-per-week: continuous.
  * Individual's working hour per week
