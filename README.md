# courses-interview-preparation-for-machine-learning-questions-in-python
Step 1: Brainstorming

What problem(s) will students learn how to solve?

How can you improve a 'Linear Regression' model to correctly predict the number of bikes rented in an hour?
How can you improve a 'Decision Tree' to accurately predict whether a customer is going to churn or not?
How can you improve a 'Logistic Regression' model to accurately classify SMS messages to Spam or ham?
How do you benchmark a 'Linear Regression' model?
How do you benchmark a 'Decision Tree' model?
How do you benchmark a 'Logistic Regression' model?
How can you convert input text into numerical values and perform text classification?
How to choose a metric that fits the business problem?
How to choose between different word vectorization methods?
How to breakdown a Linear Regression/Decision Tree/Logistic Regression Model?
How to choose between a 'Decision Tree' and 'Random Forest' algorithm for building a model?
How to overcome the problem of overfitting during the training phase?
How to differentiate between Regression and Classification problems?

What are the learning objectives of the course?

What technologies, packages, or functions will students use?

sklearn,nltk,numpy,pandas,matplotlib,seaborn,python

What terms or jargon will you define?

Chapter 1: Regression, Classification,  Feature Engineering, Feature Selection, Exploratory Data Analysis
Chapter 2: Overfitting,RMSE, MAE, R-Square, Null RMSE, Benchmarking
Chapter 3: Decision Tree, Information Gain, Entropy, Confusion Matrix, Accuracy, Sensitivity, Specificity, Pre-pruning, Post-pruning, Random Forests, Hyperparameter tuning, Ensemble Learning, Overfitting
Chapter 4: Word2Vec, Bag-of-words, N-grams, Probability, Logistic Regression,Class Imbalance, Sigmoid Function

What analogies or heuristics will you use?

Chapter 1: 

Model Improvement: You can provide a better solution to a problem only if you truly understand the problem. That is exactly what we are going to cover as part of this course. You are going to come up with a better model by understanding the given model.

Regression and Classification problems:

Feature Engineering:

Feature Selection:

Chapter 2:

Overfitting: A student who performs well during classroom discussions but fails miseably during the exam.

RMSE:

MAE:

R-Square:

Null RMSE:

Benchmarking:

Chapter 3:

Decision Tree 

Information Gain 

Entropy 

Confusion Matrix

Accuracy 

Sensitivity 

Specificity 

Pre-pruning 

Post-pruning 

Random Forests 

Hyperparameter tuning 

Ensemble Learning

Chapter 4: 

Word2Vec 

Bag-of-words 

N-grams 

Probability 

Logistic Regression

Class Imbalance 

Sigmoid Function


What mistakes or misconceptions do you expect?

It is easy to identify a regression problem from a classification problem

You can only improve a model by trying a different algorithm

You can only choose an algorithm by trial-and-error method

Accuracy is the only metric that makes sense for a given business problem

Overfitting can be easily prevented by taking less training data

One can just use frequencies of words to convert text into numberical values

What datasets will you use?

Bike Prediction Dataset
Telecom user churn
SMS message classification

Step 2:Who is this Course for?

Advanced Alex

Step 3:Course Outline

Chapter 1 - Machine Learning Interview Overview 

* *Lesson 1.1 - Types of Problems posed in a Machine Learning Interview* 
* Concepts covered: Classification and Regression problems
* Interviewer: “Here are a set of problems I want you to solve. Which of these are classification problems and which of these are regression problems? Why is it important to differentiate them?”
*  _Learning objective:_ Learner will be able to differentiate between classification and regression problems
* *Lesson 1.2 - Analyze a Machine Learning Model*
* Concepts covered: Feature Selection, Train-test data split, Model Parameters
* Interviewer:”I want you to analyze a machine learning model. How will you go about doing that?”
    * _Learning objective:_ Learner will be able to develop a systematic approach for identifying the different components of a machine learning model
* *Lesson 1.3 - Improving a Machine Learning Model *
* Concepts covered: Feature Engineering, Parameter tuning, Algorithm Selection
* Interviewer:”I want you to improve an existing model. What are the different techniques you will use to improve the model?”
    * _Learning objective:_ Learner will be able to outline the different techniques that can be used to improve the performance of an existing model

Chapter 2 - Handling a Regression Problem 

* *Lesson 2.1 - Analyze the Linear Regression Model*
* Concepts covered: Feature Selection, Linearity in a dataset
* Interviewer: “Here is a 'Linear Regression' model that was built to predict the no.of bikes rented in an hour. Can you explain the rationale behind the selection of features and the selection of algorithm for this model?”
    * _Learning objective:_ Learner will be able to formulate the feature selection process for the linear regression model given by the interviewer by performing exploratory data analysis
* *Lesson 2.2 - Evaluate the Linear Regression Model*
* Concepts covered: Regression Metrics
* Interviewer: “Now that you have understood the model, how do you evaluate this model? Which metric will you choose based on the problem at hand? Was this model overfitted?”
    * _Learning objective 1:_ Learner will be able to choose and calculate the evaluation metric that fits the regression problem posed by the interviewer
    * _Learning objective 2:_ Learner will be able to verify if the model given by the interviewer was suffering from overfitting
* *Lesson 2.3 - Benchmark the Regression Model*
* Concepts covered:  Null RMSE
* Interviewer:  “How will you benchmark the given regression model?”
    * _Learning objective:_ Learner will be able to calculate Null RMSE and benchmark the regression model given by the interviewer
* *Lesson 2.4 - Improve the Model by feature engineering*
* Concepts covered: Feature Engineering
* Interviewer: “Can you improve this model by performing feature engineering?”
    * _Learning objective:_ Learner will be able to construct a new feature that will improve the model given by the interviewer

Chapter 3 - Cracking a Classification Problem 

* *Lesson 3.1 - Analyze the Decision Tree*
* Concepts covered: Algorithm Selection, Non-linearity in a data set
* Interviewer : “Here is a decision tree that was used to predict whether a telecom user is going to churn or not. Can you explain the rationale behind the selection of features and the selection of algorithm for this model?
    * _Learning objective_: Learner will be able to reason the application of 'Decision Tree' algorithm to non-linear datasets by performing exploratory data analysis
* *Lesson 3.2 - Evaluate the Decision Tree model*
* Concepts covered:  Classification Metrics
* Interviewer: “Which evaluation metric will you choose to evaluate this Decision Tree? Was this model overfitted?” 
    * _Learning objective 1:_ Learner will be able to choose and calculate the evaluation metric that fits the classification problem posed by the interviewer
    * _Learning objective 2:_ Learner will be able to verify if the classification model given by the interviewer was suffering from overfitting or not
* *Lesson 3.3 - Benchmark the Classification model *
* Concepts covered: Null Error
* Interviewer: “How do you benchmark the given classification model?”
    * _Learning objective:_ Learner will be able to calculate Null Error and benchmark the classification model given by the interviewer
* *Lesson 3.4 - Improve the model by Parameter Tuning*
* Concepts covered: Decision Tree and Random Forest Parameters, Pre-pruning, Post-pruning
* Interviewer: “Can you improve the model by using parameter tuning? Do you think Random Forest performs better?” 
    * _Learning objective:_ Learner will be able to perform parameter tuning/select Random Forest algorithm to  improve the model given by the interviewer 

Chapter 4 - Perform text-classification using NLP

* *Lesson 4.1 - Analyze the Logistic Regression Model*
* Concepts covered: Bag-of-Words, N-grams 
* Interviewer: “Here is a Logistic Regression Model that was built to classify an SMS into spam and ham. Can you explain the rationale behind the usage of the bag-of-words technique in this model instead of N-grams? Why was the Logistic Regression algorithm chosen for this model?
    * _Learning objective 1:_ Learner will be able to differentiate between the bag-of-words and N-grams techniques
    * _Learning objective 2:_ Learner will be able to explain the rationale behind choosing 'Logistic Regression' algorithm as a benchmark for text-classification problems
* *Lesson 4.2 - Evaluate the Logistic-Regression Model*
* Concepts covered: Classification Metrics for text-classification problems
* Interviewer: “Which metric will you use to evaluate the model? Will this model work well on unseen text data?”
    * _Learning objective:_ Learner will be able to choose the evaluation metric that suits the text classification problem posed by the interviewer
* *Lesson 4.3 - Improve the model by feature engineering*
* Concepts covered: Feature Engineering for textual features
* Interviewer: “Can you improve this model using the N-gram feature engineering technique? ”
    * _Learning objective 1:_ Learner will be able to construct new features using the N-gram technique and improve the accuracy of the model given by the interviewer
    * _Learning objective 2:_ Learner will be able to justify the usage of N-gram feature engineering technique for improving a text-classification problem
* *Lesson 4.4 - Improve the model by tackling class imbalance*
* Concepts covered: Parameter tuning, Class Imbalance
* Interviewer: “How will you handle class imbalance in the given data set?”
    * _Learning objective:_ Learner will be able to tackle class imbalance by parameter tuning and improve the model given by the interviewer 



