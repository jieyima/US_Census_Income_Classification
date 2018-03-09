
# About

**This is UC Davis BAX452 Machine Learning Individual Project.**


The objective of the project is to **predict whether a person makes over 50K a year** given their demographic variations. To achieve this, several classification techniques are explored. In the end, random forest model yields to the best prediction result.

 * Source: https://archive.ics.uci.edu/ml/datasets/adult/


 * Income dataset is available at UCI machine learning website: http://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data

* Data dictionary is available at: https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.names

# How to navigate this notebook
 Below is the table of content:
<div class="toc"><ul class="toc-item"><li><span><a href="#Introduction" data-toc-modified-id="Introduction-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Introduction</a></span><ul class="toc-item"><li><span><a href="#Objective-of-the-porject" data-toc-modified-id="Objective-of-the-porject-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span>Objective of the porject</a></span></li><li><span><a href="#The-importance-of-census-statistics" data-toc-modified-id="The-importance-of-census-statistics-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>The importance of census statistics</a></span></li></ul></li><li><span><a href="#Fetching-Data" data-toc-modified-id="Fetching-Data-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Fetching Data</a></span><ul class="toc-item"><li><span><a href="#Import-Package-and-Data" data-toc-modified-id="Import-Package-and-Data-2.1"><span class="toc-item-num">2.1&nbsp;&nbsp;</span>Import Package and Data</a></span></li><li><span><a href="#Data-Dictionary" data-toc-modified-id="Data-Dictionary-2.2"><span class="toc-item-num">2.2&nbsp;&nbsp;</span>Data Dictionary</a></span></li></ul></li><li><span><a href="#Data-Cleaning" data-toc-modified-id="Data-Cleaning-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Data Cleaning</a></span><ul class="toc-item"><li><span><a href="#Dealing-with-Missing-Value" data-toc-modified-id="Dealing-with-Missing-Value-3.1"><span class="toc-item-num">3.1&nbsp;&nbsp;</span>Dealing with Missing Value</a></span></li></ul></li><li><span><a href="#Feature-Engineering" data-toc-modified-id="Feature-Engineering-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>Feature Engineering</a></span><ul class="toc-item"><li><span><a href="#Predclass" data-toc-modified-id="Predclass-4.1"><span class="toc-item-num">4.1&nbsp;&nbsp;</span>Predclass</a></span></li><li><span><a href="#Education" data-toc-modified-id="Education-4.2"><span class="toc-item-num">4.2&nbsp;&nbsp;</span>Education</a></span></li><li><span><a href="#Marital-status" data-toc-modified-id="Marital-status-4.3"><span class="toc-item-num">4.3&nbsp;&nbsp;</span>Marital-status</a></span></li><li><span><a href="#Occupation" data-toc-modified-id="Occupation-4.4"><span class="toc-item-num">4.4&nbsp;&nbsp;</span>Occupation</a></span></li><li><span><a href="#Workclass" data-toc-modified-id="Workclass-4.5"><span class="toc-item-num">4.5&nbsp;&nbsp;</span>Workclass</a></span></li><li><span><a href="#age" data-toc-modified-id="age-4.6"><span class="toc-item-num">4.6&nbsp;&nbsp;</span>age</a></span></li><li><span><a href="#Race" data-toc-modified-id="Race-4.7"><span class="toc-item-num">4.7&nbsp;&nbsp;</span>Race</a></span></li><li><span><a href="#Hours-of-Work" data-toc-modified-id="Hours-of-Work-4.8"><span class="toc-item-num">4.8&nbsp;&nbsp;</span>Hours of Work</a></span></li><li><span><a href="#Create-a-crossing-feature:-Age-+-hour-of-work" data-toc-modified-id="Create-a-crossing-feature:-Age-+-hour-of-work-4.9"><span class="toc-item-num">4.9&nbsp;&nbsp;</span>Create a crossing feature: Age + hour of work</a></span></li></ul></li><li><span><a href="#EDA" data-toc-modified-id="EDA-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>EDA</a></span><ul class="toc-item"><li><span><a href="#Pair-Plot" data-toc-modified-id="Pair-Plot-5.1"><span class="toc-item-num">5.1&nbsp;&nbsp;</span>Pair Plot</a></span></li><li><span><a href="#Correlation-Heatmap" data-toc-modified-id="Correlation-Heatmap-5.2"><span class="toc-item-num">5.2&nbsp;&nbsp;</span>Correlation Heatmap</a></span></li><li><span><a href="#age-vs.-income-level" data-toc-modified-id="age-vs.-income-level-5.3"><span class="toc-item-num">5.3&nbsp;&nbsp;</span>age vs. income level</a></span></li><li><span><a href="#Working-hour-vs.-income-level" data-toc-modified-id="Working-hour-vs.-income-level-5.4"><span class="toc-item-num">5.4&nbsp;&nbsp;</span>Working hour vs. income level</a></span></li><li><span><a href="#Occupation-vs.-Income-Level" data-toc-modified-id="Occupation-vs.-Income-Level-5.5"><span class="toc-item-num">5.5&nbsp;&nbsp;</span>Occupation vs. Income Level</a></span></li><li><span><a href="#Bivariate-Analysis" data-toc-modified-id="Bivariate-Analysis-5.6"><span class="toc-item-num">5.6&nbsp;&nbsp;</span>Bivariate Analysis</a></span></li><li><span><a href="#Race-vs.-Income-Level" data-toc-modified-id="Race-vs.-Income-Level-5.7"><span class="toc-item-num">5.7&nbsp;&nbsp;</span>Race vs. Income Level</a></span></li></ul></li><li><span><a href="#Building-Machine-Learning-Models" data-toc-modified-id="Building-Machine-Learning-Models-6"><span class="toc-item-num">6&nbsp;&nbsp;</span>Building Machine Learning Models</a></span><ul class="toc-item"><li><span><a href="#Feature-Encoding" data-toc-modified-id="Feature-Encoding-6.1"><span class="toc-item-num">6.1&nbsp;&nbsp;</span>Feature Encoding</a></span></li><li><span><a href="#Train-test-split" data-toc-modified-id="Train-test-split-6.2"><span class="toc-item-num">6.2&nbsp;&nbsp;</span>Train-test split</a></span></li><li><span><a href="#Principal-Component-Analysis-(PCA)" data-toc-modified-id="Principal-Component-Analysis-(PCA)-6.3"><span class="toc-item-num">6.3&nbsp;&nbsp;</span>Principal Component Analysis (PCA)</a></span></li><li><span><a href="#Classification-Models" data-toc-modified-id="Classification-Models-6.4"><span class="toc-item-num">6.4&nbsp;&nbsp;</span>Classification Models</a></span><ul class="toc-item"><li><span><a href="#Perceptron-Method" data-toc-modified-id="Perceptron-Method-6.4.1"><span class="toc-item-num">6.4.1&nbsp;&nbsp;</span>Perceptron Method</a></span></li><li><span><a href="#Gaussian-Naive-Bayes" data-toc-modified-id="Gaussian-Naive-Bayes-6.4.2"><span class="toc-item-num">6.4.2&nbsp;&nbsp;</span>Gaussian Naive Bayes</a></span></li><li><span><a href="#Linear-Support-Vector-Machine" data-toc-modified-id="Linear-Support-Vector-Machine-6.4.3"><span class="toc-item-num">6.4.3&nbsp;&nbsp;</span>Linear Support Vector Machine</a></span></li><li><span><a href="#Radical-Support-Vector-Machine" data-toc-modified-id="Radical-Support-Vector-Machine-6.4.4"><span class="toc-item-num">6.4.4&nbsp;&nbsp;</span>Radical Support Vector Machine</a></span></li><li><span><a href="#Logistic-Regression" data-toc-modified-id="Logistic-Regression-6.4.5"><span class="toc-item-num">6.4.5&nbsp;&nbsp;</span>Logistic Regression</a></span></li><li><span><a href="#Random-Forest" data-toc-modified-id="Random-Forest-6.4.6"><span class="toc-item-num">6.4.6&nbsp;&nbsp;</span>Random Forest</a></span></li><li><span><a href="#K-Nearest-Neighbors" data-toc-modified-id="K-Nearest-Neighbors-6.4.7"><span class="toc-item-num">6.4.7&nbsp;&nbsp;</span>K-Nearest Neighbors</a></span></li></ul></li><li><span><a href="#Cross-Validation" data-toc-modified-id="Cross-Validation-6.5"><span class="toc-item-num">6.5&nbsp;&nbsp;</span>Cross Validation</a></span><ul class="toc-item"><li><span><a href="#GridSearch" data-toc-modified-id="GridSearch-6.5.1"><span class="toc-item-num">6.5.1&nbsp;&nbsp;</span>GridSearch</a></span></li></ul></li></ul></li><li><span><a href="#Reflection" data-toc-modified-id="Reflection-7"><span class="toc-item-num">7&nbsp;&nbsp;</span>Reflection</a></span></li></ul></div>

# Visualization Excerpts
### 1. Gini Index for US:

A measure of statistical dispersion intended to represent the income or wealth distribution of a nation's residents, and is the most commonly used measure of inequality.

Source: [Gini coefficient](https://en.wikipedia.org/wiki/Gini_coefficient)
![image.png](http://www.jbencina.com/blog/wp-content/uploads/2015/07/2013-Household-Income-County-Inequality.png)

### 2. Violin Plot
This is a violin plot using matplotlib to show how different occupations yield to salary variations, controlling age variables.  
<img width="1433" alt="violinplot" src="https://user-images.githubusercontent.com/31974451/36577090-d25dc36a-1809-11e8-98b7-88c18805faed.png">

### 3. Bivariate Analysis
Bivariate analysis is one of the simplest forms of quantitative (statistical) analysis.[1] It involves the analysis of two variables (often denoted as X, Y), for the purpose of determining the empirical relationship between them.

Source: [Bivariate Analysis](https://en.wikipedia.org/wiki/Bivariate_analysis)
<img width="1232" alt="bivariate variables" src="https://user-images.githubusercontent.com/31974451/37197590-33b9175a-2330-11e8-85af-838cbeabec8a.png">

### 4. Principal Component Analysis
A statistical procedure that uses an orthogonal transformation to convert a set of observations of possibly correlated variables into a set of values of linearly uncorrelated variables called principal components.

Source:
- [Bivariate Analysis: wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)
- [Bivariate Analysis: Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/05.09-principal-component-analysis.html)

![PCA](https://user-images.githubusercontent.com/31974451/37197639-5db84a76-2330-11e8-9a78-0628fa49f87f.png)


# Data dictionary

Extraction was done by Barry Becker from the 1994 Census database. A set of reasonably clean records was extracted using the following conditions: ((AAGE>16) && (AGI>100) && (AFNLWGT>1)&& (HRSWK>0))

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
