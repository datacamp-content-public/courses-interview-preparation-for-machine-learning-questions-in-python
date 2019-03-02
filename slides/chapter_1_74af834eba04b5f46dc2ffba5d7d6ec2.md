---
title: Insert title here
key: 74af834eba04b5f46dc2ffba5d7d6ec2

---
## Null RMSE

```yaml
type: "TitleSlide"
key: "cdd8593aee"
```

`@lower_third`

name: Sai Charan Tej
title: Product Manager


`@script`
In the previous lesson, you have learnt how to check for overfitting in your model. In this lesson, we are going to answer one of the basic ML Interview questions - How do you benchmark your model?


---
## Exercise

```yaml
type: "FullSlide"
key: "2a96d7ae22"
```

`@part1`
I will benchmark my model by comparing my model's RMSE with the RMSE of:

a.A new model with a different set of input features  

b.A model that always predicted the average 

c.A model that always predicted the correct value 

d.A model that always predicted the wrong value


`@script`



---
## How do you benchmark the model you have built?

```yaml
type: "TwoColumns"
key: "84f6b5b099"
```

`@part1`
Interviewer:The RMSE value of your base model is 164.637 {{1}}

**Does this RMSE value represent a good model or a below-average model?** {{2}}

Let us find out by benchmarking your model! {{3}}


`@part2`
![](https://assets.datacamp.com/production/repositories/4715/datasets/ec28afc57ce07e13b522943efdb57104fe8a1c7c/benchmark.jpg){{2}}


`@script`
Now the interviewer asks you a different question. Just how good is your model? Does the RMSE value represent a good model or an average model? You answer this question by benchmarking your model!


---
## What exactly is model benchmarking?

```yaml
type: "TwoColumns"
key: "5a78ebdebb"
```

`@part1`
- You compare your base model's performance with that of a (**stupid**) model that predicts the output without the help of input features. {{1}}

- The RMSE of this stupid model is called 'Null RMSE' {{2}}

- Any machine learning model you build should do better than this stupid model. {{3}}


`@part2`
![](https://assets.datacamp.com/production/repositories/4715/datasets/3ac7f429f4b159a6ba51d31dc9a5e3458285d25b/benchmark-rmse.jpg){{2}}


`@script`
What is model benchmarking?
You compare your model’s performance with that of a stupid model. What is a stupid model? A model that tries to predict without considering input features. I call this model stupid, since it is practically making predictions without data.


---
## How do you build a stupid model?

```yaml
type: "FullSlide"
key: "fd5681da11"
```

`@part1`
![](https://assets.datacamp.com/production/repositories/4715/datasets/de426914547a8980eddb150374b758d26553d0ee/output.png)


`@script`
Now how do you build a stupid model? Assume that you are trying to predict the total bike rentals in an hour without the help of any of these input features.


---
## How does a stupid model predict?

```yaml
type: "FullSlide"
key: "b00e10b99a"
```

`@part1`
If you are to tell the owner of the bikestore, the number of bikes that are going to be rented in the next hour, which of the below estimates will you choose?

a.Random Guess 

b.Average number of bikes rented per hour 

c.Max number of bikes rented per hour 

d.Min number of bikes rented per hour 

**Answer: b ** {{1}}


`@script`
You have to make a prediction and tell the bikestore owner. Which of these options will you choose?
Your prediction should be the average number of bikes rented per hour.


---
## Why does predicting the mean make sense?

```yaml
type: "TwoColumns"
key: "6e6a7d7210"
```

`@part1`
- Central Tendency states that majority of values in a distribution lie around the center. {{1}}
- This is the best prediction you can make in the absence of input features {{2}}


`@part2`
![](https://assets.datacamp.com/production/repositories/4715/datasets/31602aabca0fa5fb0ddd86bcff7bd91c2f2c0d82/central-tendency-copy.jpg){{1}}


`@script`
Why is the mean a good prediction?
Central tendency. According to central tendency, majority of the values in a distribution lie around the center. In the absence of input features, a central tendency measure like mean is your best bet.


---
## Benchmarking

```yaml
type: "FullSlide"
key: "cf60a44c5a"
```

`@part1`
Below are the steps to benchmark your model:

1.Split the data into training data and test data

2.Calculate the Average Number of Bikes Rented every hour for the test data. This becomes the prediction of the stupid model.

3.Calculate the Null RMSE value by taking into consideration these predictions

4.Verify whether your base model's RMSE value is lower than Null RMSE or not


`@script`
Now that we have built a stupid model, let us lay down the process for benchmarking your base model.
You first split the data into training and testing data.
Build a stupid model with the mean value of bikes rented as its prediction
Calculate Null RMSE value with this prediction
Verify whether your base model’s RMSE value is lower than Null RMSE or not.


---
## Step 1: Split the data into training and test data

```yaml
type: "FullSlide"
key: "2928632209"
```

`@part1`
```python
# split X and y into training and testing sets
X_train, X_test, y_train, y_test = 
train_test_split(X, y, random_state=3)```


`@script`
You split the data using the same random_state value that you have used when splitting the data for your base_model. This will help us in comparing your base_model with the stupid_model.


---
## Step 2: Calculate the mean response value

```yaml
type: "FullSlide"
key: "a3a5996483"
```

`@part1`
We create and fill an array **y_null** with the average number of bikes rented per hour
```python
# create a NumPy array with the same shape as y_test
y_null = np.zeros_like(y_test, dtype=float)

# fill the array with the mean value of y_test
y_null.fill(y_test.mean())
print(y_null)
```
**Output:** [190.732,190.732,......190.732]


`@script`
You initialize an array y_null and fill it with the average of the output variable in the test data for all the test samples.


---
## Step 3: Calculate Null RMSE

```yaml
type: "FullSlide"
key: "fff65c249c"
```

`@part1`
```python
# fill the array with the mean value of y_test
y_null.fill(y_test.mean())
# compute null RMSE
null_rmse = np.sqrt
(metrics.mean_squared_error(y_test, y_null))
print (null_rmse)
```
**Output:** 180.448


`@script`
You calculate the null RMSE just like how you calculated RMSE value for your base model.  The only difference is that the average value becomes the predicted value for this stupid model.


---
## Step 4: Benchmark your model against Null RMSE

```yaml
type: "FullSlide"
key: "16e00dbbc0"
```

`@part1`
Now you can compare the **RMSE value of your base model** against the **null_rmse**.
```python
if rmse_base_model < null_rmse:
 print('Your model is better than a stupid model')
else:
 print('Your model is worse than a stupid model')
```
**Output:** You model is better than a stupid model


`@script`
Finally, you verify if your base model’s RMSE is lower than null RMSE or not. If it is lower, then your model is a good model. If it is not, you have built a model so bad that you are better off not building a model in the first-place.


---
## Exercise - Solution

```yaml
type: "FullSlide"
key: "bfe4077f6e"
```

`@part1`
I will benchmark my model by comparing my model's RMSE with the RMSE of:

a.A new model with a different set of input features  

**b.A model that always predicted the average **

c.A model that always predicted the correct value 

d.A model that always predicted the wrong value


`@script`



---
## Summary

```yaml
type: "FullSlide"
key: "28f258b8d7"
```

`@part1`
In order to benchmark your model, you need to:

1.Build a stupid model which predicts the output in the absence of input features {{1}}

2.Calculate the Null RMSE for this stupid model {{2}}

3.Verify whether your base model's RMSE is above or below the Null RMSE {{3}}


`@script`
To summarize, in this lesson we have learnt how you can benchmark your machine learning model:
1.We first build a stupid model that makes predictions without input features
2.We then calculate the RMSE value of this stupid model.
3.Verify whether your base model is better than this stupid model or not.


---
## Let's practice!

```yaml
type: "FinalSlide"
key: "41126c3cf3"
```

`@script`


