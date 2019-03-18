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

Regression vs Classification: If somebody is particularly asking about the marks you obtained in the exam, then they are interested in 'Regression' problem. If they are only interested in whether you passed or failed, then they are looking at a 'Classification' problem. You need to understand what they are interested in, before you give out your response. Similarly, you need to understand the type of problem you are dealing with, before deciding the approach towards solving that problem. 


Model Improvement: You are given the responsibility of making a student better through training. What is the first thing you should do? You cannot randomly start teaching him everything you know. You first need to analyze the performance of a student, identify his strengths and weaknesses and then come up with a plan to improve his performance. That is exactly what you need to do while improving an existing model. You need to first understand how the model was built, why certain features are selected, benchmark the performance of the model and then set about improving its performance.  

Feature Engineering: Say, you are planning to go to your friend's house. You will go only if your friend's house is within a reasonable distance. You called him up and asked for the distance and he said "The latitude location of my house is 23.6 and the longitude location is 31.2". Can you really make up your mind as to whether visit your friend or not by using these coordinates? Stand-alone, each of those attributes is not going to help you. Can your friend do better? Imagine, he calculated the distance between both houses using these coordinates. That will give you exactly the information you need to make your decision. Just like how the 'Distance' feature which was engineered from the 'Latitude' and 'Longitude' features, helped you in making a better decision, in machine learning too, you can improve the performance of a model by engineering a new feature that makes sense.

Feature Selection: Say, you want to predict the salary of an employee in your organization. You have features like Gender, Age, Work Experience. If all of them are female, does the 'Gender' feature really matter? 

Chapter 2:

Overfitting: A overfitted model is like a student who performs well during classroom discussions but fails miseably during the exam.

RMSE: Root Mean Square Error is like the metric that you use to how well the student has peformed in a test that contains questions that he has not seen earlier. You use this metric, when you want to punish the student for committing more mistakes while answering the most difficult questions in the exam compared to answering the easier questions in the exam.

MAE: It is similar to RMSE except that here, you punish the student equally irrespective of the difficulty of the question.

R-Square: It kind of tells how well a student has prepared for the exam. You use to evaluate how good is the 'Best Fit Line' on training data.

Null RMSE: It is the RMSE value of a stupid model that makes predictions without any input data. 

Benchmarking: Benchmarking is the process of quantifying how good you really are by comparing with a standard. This standard in the case of a 'Machine Learning' model would be 'Null Error'

Chapter 3:

Decision Tree : It is similar to the approach you follow to decide the company you want to join. You make a series of decisions, first you decide whether the package offered is more or less compared to your current job. Then you decide whether the job is in your hometown or in a different city. Then, you decide whether the work culture in that company is good or bad. You finally make your decision, by considering all these factors (package,location,work culture). This is exactly what a decision tree represents - a series of decisions that will help you make the right prediction. 

Information Gain : Among the multitude of decisions that you are faced with, how are you going to decide the order in which you need to take these decisions? You will first take the decision that results in the maximum information gain. For example, if work culture is the most important parameter for you, then you eliminate the companies that have bad work culture first and then proceed onto those companies with good work culture. Now that you have gained more clarity in your choice of a company, you proceed further to evaluate the salary offerings by the prospective companies. Similarly, a decision tree also considers features based on the information gain attributed to that feature.

Entropy: Entropy is a measure to quantify how confused you were when you had to consider all these multiple factors (work culture, package,location) while deciding your new job. Just like how you would be systematically evaluating all these factors based on the information gained and reduce confusion while making your final decision, a decision tree also considers features in a way that the entropy value decreases as we build the tree. 

Confusion Matrix: How do you evaluate how well you performed in an exam that contains two types of questions - hard and easy? You need to see the actual answers and the answers given by you.Similarly, a confusion matrix also lays out your responses to both the hard and easy questions along with how accurate you are with your predictions. 

Accuracy : How many questions did the student answered correctly out of the total no.of questions?

Sensitivity/Recall: Out of all the hard questions, how many did the student answer correctly?

Specificity: Out of all the easy questions, how many did the student answer correctly?

Precision: When a student answers a hard question, how often is he correct?

Pre-pruning: Say, you are considering close to 15 factors for deciding which company you want to join. There are frankly more than 3000 combinations of these factors you can think of. Sounds scary, isn't it? How can you overcome this 'Death by choices' scenario? You restrict the number of combinations, say I will consider only 5-10 combinations. That is exactly what pre-pruning does to a decision tree. It puts a cap on the number of branches a decision tree can have.

Post-pruning: Say, if you have all the time in the world to make a decision about the company you want to join, then you can evaluate all possible combinations of factors and then eliminate those paths that do not make any sense. This is what we mean by post-pruning a decision tree where we allow the decision tree to be constructed before cutting the unwanted branches. 

Random Forest: When you are faced with the prospect of choosing the company you want to join, will you be considering a single person's opinion or the opinion of multiple people? You usually check with your friends, colleagues, family etc. Why? Can't you just go with a single person's opinion? We do not usually just take a decision based on a single person's input because we know that his opinion can be biased. We consider multiple people's opinions to ensure that we are not making biased decisions. Similarly, a random forest algorithm constructs not one decision tree, but many many decision trees (hundreds of them) to help classify a sample.  

Parameter tuning: How does a mathematics teacher improve his teaching skills? By fine-tuning his usage of examples, his delivery of subject matter, empathizing with the students, adapting to the demands of the class etc. This is exactly what parameter tuning means. Just like the teacher, a model can also be improved by fine-tuning its parameters.  

Ensemble Learning: Just like how a great movie has contribution from all its cast members an ensemble learning algorithm has contribution from a combination of models. Random Forest is an ensemble learning technique that takes inputs from a collection of decision trees before predicting the output.

Chapter 4: 
 
Bag-of-words: Say, you want to communicate with someone who understands only numbers. You speak text and they understand numbers. One way to solve this communication gap is to assign numbers to all the words you know and assign these values to the words in your sentences. Because the other person is good with numbers, he will make the necessary mappings and understand what you are trying to say. This is what 'Bag-of-words' technique means.   

TF-IDF Score: TF-IDF corresponds to assigning a score based on the importance of a word rather than the frequency of appearance of a word. Supposed, if the words 'The' and 'Nadal' are repeating the same number of times in a document, the word 'Nadal' provides more context about the type of document (it is a sports document) than the word 'the', since 'the' appears in pretty much every document about every sport in the world.

N-grams:N-grams is similar to bag-of-words except that it maintains the order of words, which if you look at it, is pretty important while making sense of any statement.

Probability: If you throw a coin 100 times, how many times do you think it shows up as a head? 50. Why? Because, there is always an equal chance that whenever a throw a coin, it can show up as a head or tail. Probability is nothing but the ratio of the outcomes you are interested in, in our case number of heads, to the all possible outcomes.  

Logistic Regression: Imagine you are given the task of analyzing loan applications and deciding which applications to reject and which applications to accept. What kind of information do you need to take this decision? If someone can give you a probability of default for every loan application, wouldn't your life be so much easy? That is exactly what a Logistic Regression model does. It takes into account the input features and outputs a probability value that represents the chance that a sample belongs to a particular class. 

Class Imbalance: Say, you are blind-folded and have to classify two types of swans in a group of 100 swans. 95 of them are white swans and only 5 of them are black swans. You used your intelligence like analyzing the sounds made by swans, trajectory patterns etc and had 95% accuracy in your predictions. But did you really do well? If you look at it, even if you randomly made predictions, you will select a white swan 95 out of 100 times. The hardest part is to identify the 5 black swans. This is what we call as 'Class Imbalance'. 

Sigmoid Function: Do you remember how your grades are always on the scale 1-4 even though your exam marks are in the range of 100 or 1000? Your grades are obtained by standardizing your exam scores. Why was it done? It would be easier to compare grades than actual marks as different students might take different tests - some tests score out of 100, some of them score out of 1000. Similarly, sigmoid function transforms numerical values to probabilities whose values lie between 0 and 1. 


What mistakes or misconceptions do you expect?

The approach towards feature selection is the same - irrespective of whether the problem is a regression problem or a classification problem

You can only improve a model by trying a different algorithm

You can only choose an algorithm by trial-and-error method

Accuracy is the only metric that makes sense for any given business problem

Overfitting can be easily prevented by taking less training data or choosing a different algorithm

One can just use frequencies of words to convert text into numerical values

Feature Scaling is needed for Decision Tree models

In order to benchmark a model, you need to refer to pre-defined industry standard metrics for accuracy, rmse etc

Feature Engineering is creating new features that may not be based on the input features

Parameter tuning will not significantly improve the performance of a model

Text-classification problems seem to be approached the same way as any other classification problem

Evaluating a text-classification model is the same as that of evaluating any other classification problem

If somebody asks to dissect/describe a model, we only need to focus on the algorithm used and the accuracy of the model 

Feature Selection and Feature Engineering are not so important as algorithm selection

You just randomly try different combinations of features and algorithms and eventually you will stumble across an accurate model

How the model performs on training data is more important than how it performs on unseen data

What datasets will you use?

Bike Prediction Dataset:https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset#
Classifying Senators to be Democrat or Republican: https://archive.ics.uci.edu/ml/machine-learning-databases/voting-records/house-votes-84.names
SMS Message Classification: https://archive.ics.uci.edu/ml/datasets/sms+spam+collection
Optional Datasets:
Predicting the Salary levels:https://www.kaggle.com/eltonpaes/adult-salary-prediction/data 
Predicting NYC Tax Duration:https://www.kaggle.com/c/nyc-taxi-trip-duration/data
Predicting the movie genre based on plot: https://www.kaggle.com/aminejallouli/genre-classification-based-on-wiki-movies-plots

Step 2:Who is this Course for?

The course is structured to simulate the actual machine learning interview experience for students who fit the description of 'Advanced Alex'. Students will be asked to analyze and improve an existing model. Instructor lectures will be providing feedback to the students on their choices and results.The objective for the students is to improve the existing model by leveraging the techniques described in the course.

*Course Requirements:*

1.Course is for students (Advanced Alex) who have gone through other Machine Learning tracks and are preparing for interviews.
2.Students are expected to have good knowledge of Pandas, sklearn, Nltk, Numpy and Seaborn packages
3.Students are expected to know the steps to build the basic Linear Regression, Logistic Regression, Decision Tree and Random Forest models


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



