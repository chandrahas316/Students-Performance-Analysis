<a name="br1"></a>**Report**

**Students Performance Analysis**

**Group members -**

● Basavachari Boppudi (S20200010043)

● Tummepalli Anka Chandrahas Purushotham Gupta

(S20200010213)

**Outline -**

● Problem statement
● Objective

● Dataset

● Methodology ● Code summary




<a name="br2"></a>**Problem statement -**

● Do Exploratory Data Analysis (EDA) for the students performance in exams

dataset and build a model for classifying these students.

**Objective -**

● The objective of this project is to do EDA and try different models for the

classification and choose the best model. We used Random Forest classifier,
Decision tree, K-neighbors classifier and Logistic Regression.

**Dataset -**

● We have taken the [**Students**](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[** ](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[Performance**](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[** ](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[in**](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[** ](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[Exams**](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)[** ](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)dataset from kaggle

which is about the marks secured by the students. The attributes in the
dataset are as follows

○ gender - Gender of the student (categorical -[male,female])
○ race/ethnicity - race of the student (categorical - [group A, group B,
 group C, group D, group E])

○ parental level of education - highest degree of parents (categorical -
 [bachelor’s degree, some college, master’s degree, associate’s degree,
 high school, some high school])

○ lunch - lunch fee for the student (categorical - [standard,

free/reduced])

○ test preparation course - students status whether a course has been
 taken and completed or none (categorical - [none, completed])
○ math score - student performance in math test (numerical)
○ reading score - student performance in reading test (numerical)
○ writing score - student performance in writing test (numerical)




<a name="br3"></a>● Data sample

**Methodology -**

● Importing Data ● Data preparation

● Data preprocessing

○ Checking for null values

` `○ Checking datatypes of each attribute
 ○ Correlation between each attribute
● Data Visualization

● Model

○ Splitting train and test set using train\_test\_split
○ Checking evaluation metrics for Random Forest classifier, Decision
 tree, K-neighbors classifier and Logistic Regression to choose the best
 model for this dataset.

● Results

● Conclusion

**Code summary -** Importing data

● Importing dataset into a pandas dataframe.




<a name="br4"></a>Data Preparation

● We added an attribute called ‘percentage’ to the dataset by taking the

average of all 3 scores of a student.

● After adding ‘percentage’ attribute to the dataset,

Data Preprocessing

● We checked for null values in the dataset

There are no null values in the dataset

● We check what are the datatypes of each attribute in the dataset

There are 5 categorical attributes and 4 numerical attributes in the dataset




<a name="br5"></a>● Checking for correlation among attributes. First we converted all the

categorical attributes into numerical using the label encoder method in
sklearn library. Heat map for correlation matrix is as follows

There is no correlation between independent attributes or independent and
dependent attributes.




<a name="br6"></a>Data Visualization

● This plot is about number of students in each group in the race/ethnicity

attribute

● We can see that group C has the highest number of students and group A has

the lowest

● This plot is about number of students in each gender in gender attribute
● Students are almost equally distributed between male and female.




<a name="br7"></a>● This plot is about number of students in each parent’s level of education
● Most parent’s education is some college and associate degree is second

highest with not much difference. Least is master's degree.

● This plot is about the number of students distributed in the lunch attribute.
● Most of the students(64.5%) are paying standard fees.




<a name="br8"></a>● This plot is about the number of students distributed in test preparation

course attribute.

● Most of the students(64.2%) have not taken any test preparation course.

● This density-Percentage plot gives the probability distribution of percentage

with various classes.




<a name="br9"></a>● These are the bar plots of the score vs gender and score vs race/ethnicity.
● Females have achieved highest in both reading and writing score but Males
 get the highest in Math score.

● Group E got the highest score in all 3 scores among the groups.




<a name="br10"></a>● Parental having of Master’s degree students got the highest score than others
● Students taking Standard lunch got the highest score than free lunch.

● Almost all the scores are in normal distribution for both genders.




<a name="br11"></a>● The pair plot all scores for each other.

● It states that all the scores are correlated positively as we can see the contour

along the ‘x=y’ line.




<a name="br12"></a>● These are the box plot for parents level of education, gender, race/ethnicity

and lunch attributes

● There are very few outliers in the dataset which are not really necessary to

remove.




<a name="br13"></a>**Model -**

● These are the unique values present into the categorical attributes

● We added a new attribute called grade for classification using the following

piece of code

After doing it the dataset is like

Value counts of each grade are as shown **→**

So, the target variable is grades.




<a name="br14"></a>● We did one more encoding scheme using the get\_dummies method in the

pandas library for this dataset to get understanding of different encoding
methods.

● We defined a custom transformer named student\_transform which is like a

preprocessing step for model pipeline. We used 4 different ML models
which are Random Forest classifier, Decision tree, K-neighbors classifier,
and Logistic Regression.

● We did train\_test\_split with test size as 20%

● For the model we created a pipeline which includes 3 steps

○ Student\_Transformer - This is a preprocessing step which removes

grades attribute.

○ StandardScalar - This step is to normalize the data using z - score

normalization method.

○ Classifier - This step is for training of the 4 models which are

mentioned above.




<a name="br15"></a>● Evaluation metrics used are - confusion matrix, accuracy, balanced accuracy,

sensitivity, specificity and ROC curve.




<a name="br16"></a>**Results**

● Evaluation results for random forest classifier




<a name="br17"></a>● Evaluation results for *Decision tree* classifier



<a name="br18"></a>● Evaluation results for K-neighbors classifier




<a name="br19"></a>● Evaluation results for Logistic regression classifier

**Conclusion -**

From the above ROC curve we can conclude that **Logistic Regression** gives the best results for the classification as it has the largest AUC.
