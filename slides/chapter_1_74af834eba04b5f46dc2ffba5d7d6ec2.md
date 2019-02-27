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
title: 


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

- Does the above RMSE value represent a good model or a below-average model? 
- How do you benchmark it?


`@script`



---
## Introducing Null RMSE

```yaml
type: "FullSlide"
key: "0118f387bd"
```

`@part1`
Imagine your dataset does not contain any input variables. How will you predict the number of bikes rented?


`@script`



---
## Predicting the mean

```yaml
type: "FullSlide"
key: "f6c3b2de0b"
```

`@part1`
In this situation, your best guess would be the mean. For all the different time periods, you will always be predicting the mean response value.

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
Now calculate the RMSE value of this stupid model which always predicts the output to be the mean number of bikes rented.
```python
# fill the array with the mean value of y_test
y_null.fill(y_test.mean())
y_null
# compute null RMSE
null_error = np.sqrt(metrics.mean_squared_error(y_test, y_null))
print (null_error)
```
null_error represents how well(bad!) the model would be behaving in the absence of input variables


`@script`



---
## Benchmark your model against Null RMSE

```yaml
type: "FullSlide"
key: "16e00dbbc0"
```

`@part1`
Now you can compare the RMSE value of your base model against the null_error.
```python
if base_model_performance < null_error:
   print ('Your model is better than a random prediction')
else:
   print ('Your model is worse than a random prediction')
```
> If the base model RMSE is more than that of null_error, then your model is no good than a stupid model which always predicted the mean value (you are actually making it worse by deploying Machine Learning).


`@script`



---
## Takeaway

```yaml
type: "FullSlide"
key: "28f258b8d7"
```

`@part1`
# You should always strive to build models whose RMSE value is less than the Null RMSE value for the model


`@script`



---
## Let's practice!

```yaml
type: "FinalSlide"
key: "41126c3cf3"
```

`@script`


