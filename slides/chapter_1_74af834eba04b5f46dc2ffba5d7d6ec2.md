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



---
## How do you benchmark the model you have built?

```yaml
type: "FullSlide"
key: "4668c301c5"
hide_title: false
```

`@part1`
Interviewer:The RMSE value of your base model is 164.65. 
```python
base_model_performance = train_test_eval(['temp'])
print (base_model_performance)
``` 
Output: 164.637

- Does the above RMSE value represent a good model or a below-average model? {{1}}
- How do you benchmark it? {{2}}


`@script`



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

**Answer: b** {{5}}


`@script`



---
## What exactly is model benchmarking?

```yaml
type: "FullSlide"
key: "54d7dc43dc"
```

`@part1`
Benchmarking a model corresponds to understanding how a model would predict the output in the absence of input features.

The performance of this model, a stupid model, represents the best a model can do in predicting the output without the help of input features.


`@script`



---
## Scenario

```yaml
type: "FullSlide"
key: "b00e10b99a"
```

`@part1`
Imagine you just have details about the no.of bikes rented every hour. If you are to tell the owner of the bikestore, the number of bikes that are going to be rented in the next hour, which of the below estimates might come to your rescue?

a.Random Guess

b.Average number of bikes rented per hour

c.Max number of bikes rented per hour

d.Min number of bikes rented per hour

**Answer: b **


`@script`



---
## Predicting the mean

```yaml
type: "FullSlide"
key: "f6c3b2de0b"
```

`@part1`
In this situation, your best guess would be the mean. For all the different time slots, you will always be predicting the mean response value. Why?

Central Tendency states that majority of values in a distribution lie around the center. So, it would make a lot of sense if you recommend the average number of bikes to the bikestore owner when you do not have any input features at your disposal.


`@script`



---
## What is Null RMSE?

```yaml
type: "FullSlide"
key: "a325fd6176"
```

`@part1`
Null RMSE is the RMSE of the model that always predicts the mean value for the input training samples. 

In our case, we calculate null RMSE by taking the difference between the average number of bikes rented per hour (predicted value) and the actual bikes rented per hour


`@script`



---
## Calculate Null RMSE

```yaml
type: "FullSlide"
key: "cf60a44c5a"
```

`@part1`
Below are the steps:

1.Split the data into training data and test data

2.Calculate the Average Number of Bikes Rented every Hour for the test data. This becomes your prediction.

3.Calculate the Null RMSE value by taking into consideration these predictions

4.Verify if your base model's RMSE value is lower than Null RMSE


`@script`



---
## Calculate the mean response value

```yaml
type: "FullSlide"
key: "a3a5996483"
```

`@part1`
We create an array y_null that has predicted the no.of bikes rented for all the test samples to be the mean
```python
# split X and y into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=3)

# create a NumPy array with the same shape as y_test
y_null = np.zeros_like(y_test, dtype=float)

# fill the array with the mean value of y_test
y_null.fill(y_test.mean())
y_null
```


`@script`



---
## Calculate RMSE

```yaml
type: "FullSlide"
key: "fff65c249c"
```

`@part1`
Now let us calculate the RMSE value of this stupid model which always predicts the output to be the mean number of bikes rented.
```python
# fill the array with the mean value of y_test
y_null.fill(y_test.mean())
y_null
# compute null RMSE
null_error = np.sqrt(metrics.mean_squared_error(y_test, y_null))
print (null_error)
```
**null_error** represents how well(bad!) the model would be behaving in the absence of input variables


`@script`



---
## Benchmark your model against Null RMSE

```yaml
type: "FullSlide"
key: "16e00dbbc0"
```

`@part1`
Now you can compare the **RMSE value of your base model** against the **null_error**.
```python
if base_model_performance < null_error:
   print ('Your model is better than a random prediction')
else:
   print ('Your model is worse than a random prediction')
```
> If the base model RMSE is **more than that** of null_error, then your model is no good than a stupid model which always predicted the mean value (you are actually making it worse by deploying Machine Learning).


`@script`



---
## Takeaway

```yaml
type: "FullSlide"
key: "28f258b8d7"
```

`@part1`
# You should always strive to build models whose RMSE value is less than the Null RMSE value for the model!


`@script`



---
## Let's practice!

```yaml
type: "FinalSlide"
key: "41126c3cf3"
```

`@script`


