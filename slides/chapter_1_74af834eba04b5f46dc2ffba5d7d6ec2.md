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
In the previous lesson, you have found out that your model is not overfitted.


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
Just how good is your model? That is what the interviewer asks. How do you interpret the RMSE value?


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
You compare the RMSE of your base model with that of a stupid model that tries to predict the output without the help of input features. The RMSE of this stupid model is called the Null RMSE. You should always strive to ensure that your Model's RMSE is lower than the RMSE of this stupid model.


---
## How do you build a stupid model?

```yaml
type: "FullSlide"
key: "fd5681da11"
```

`@part1`
![](https://assets.datacamp.com/production/repositories/4715/datasets/de426914547a8980eddb150374b758d26553d0ee/output.png)


`@script`
Let us take a scenario. You have to predict the total rentals without the help from input features like 'Date and time','Season', 'Weather','Humidity'


---
## How does a stupid model predict?

```yaml
type: "FullSlide"
key: "b00e10b99a"
```

`@part1`
If you are to tell the owner of the bikestore, the number of bikes that are going to be rented in the next hour, which of the below estimates will you choose?

a.Random Guess {{1}}

b.Average number of bikes rented per hour {{2}}

c.Max number of bikes rented per hour {{3}}

d.Min number of bikes rented per hour {{4}}

**Answer: b ** {{5}}


`@script`
To understand how a stupid model makes predictions, let us try one for ourselves. Imagine you are trying to make predictions in the absence of input features, you have to tell the bike owner the number of bikes that are going to rented in the next hour. Which of the below estimates will you choose? Of all these responses, mean makes more sense.


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
Central Tendency. Majority of the values lie around the center. As you have no input features to rely on, you choose mean as it represents the majority of observations in the output variable. For all the different time slots, you will always be predicting the mean response value.This is the best prediction you can make in the absence of input features.


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
Now that we know how to build a stupid model, let us lay down the steps in the process of benchmarking. You first split the data into training and test data. Calculate the Average no.of bike rentals per hour. This becomes the prediction of the stupid model. Calculate the Null RMSE value for this stupid model just the way you calculate RMSE value for any model. Finally, verify whether your base model's RMSE value is lower than Null RMSE or not.


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
We are maintaining the same random_state value to compare how the stupid model performs compared to your base_model.


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
y_null
```


`@script`
Here we initialize an array y_null and fill it with the average number of bikes rented per hour value for all the test data points.


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
Output: 190.732


`@script`
Now let us calculate the RMSE value of this stupid model which always predicts the output to be the mean number of bikes rented. null_rmse represents how well(bad!) the model would be behaving in the absence of input variables


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
If the base model RMSE is **more than that** of null_error, then your model is no good than a stupid model which always predicted the mean value (you are actually making it worse by using Machine Learning).


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
To summarize, for benchmarking any machine learning model you build, you first need to build a stupid model that always predicts the output to be the mean value. Calculate the Null RMSE for this model. And then verify whether your base model's RMSE is above or below the Null RMSE. If it is below, your model is a really good model. If it is above, then your model is not so great and you need to go back to the drawing board to better it.


---
## Exercise

```yaml
type: "FullSlide"
key: "2a96d7ae22"
```

`@part1`
I will benchmark my model by comparing my model's RMSE with the RMSE of:

a.A new model with a different set of input features {{1}} 

b.A model that always predicted the average {{2}}

c.A model that always predicted the correct value {{3}}

d.A model that always predicted the wrong value {{4}}


`@script`



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
## Let's practice!

```yaml
type: "FinalSlide"
key: "41126c3cf3"
```

`@script`


