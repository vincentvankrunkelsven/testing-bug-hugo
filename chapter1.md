---
title       : Conversion between temperature measures
description : In this chapter you will practice the basic functionalities of Python, including calculations, variable assignments, built-in functions and methods. We will also work on some basic manipulations of lists. Let's get started!
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf


--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:8c8181cc6b
## Hot n' cold
Fahrenheit and Celsius are the two most common measures for temperature, but for someone used to one system, a number in the other system might make little sense. Now, let's use Python to convert 30 degrees Celsius to Fahrenheit using the formula `$T(F) = T(C)*\frac{9}{5} + 32$`, and get a sense of how hot that is.  

*** =instructions
- 80
- 84
- 86

*** =hint
- You can use `(a/b)` to denote a fraction.

*** =pre_exercise_code
```{python}

```

*** =sct
```{python}
msg1 = """Check your calculation."""

msg2 = """Check your calculation."""

msg3 = """Yes!"""

test_mc(3, [msg1, msg2, msg3])
```

--- type:NormalExercise lang:python xp:50 skills:1 key:514818b19a
## Using variables to store values

A lot of times we need to save the values and pass them to other calculations. In such cases we can assign values to variables. In this exercise, we already assigned a temperature in Celsius to the variable `cel`. Convert it to Fahrenheit and save it to the variable `fah`. Then find the type of `fah`. Again, the formula to convert temperature is `$T(F) = T(C)*\frac{9}{5} + 32$`.

*** =instructions
- Convert `cel` from Celsius to Fahrenheit.
- Find the type of BMI and print it.
- Hit "submit answer" to print the result.

*** =hint
- In your calculations, you can use variables as if they are numbers.
- Use `type(a)` to find the type of the variable `a`.
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
cel = 26
```

*** =sample_code
```{python}
# Convert cel from Celsius to Fahrenheit: fah
fah = cel*(9/5)+32

# Print the type of fah
print(type(fah))
```

*** =solution
```{python}
# Convert cel from Celsius to Fahrenheit: fah
fah = cel*(9/5)+32

# Print the type of fah
print(type(fah))

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("BMI")
#test_function("print", index=1, incorrect_msg="Did you find the type of BMI?", not_called_msg="You don't need to change the code for the print statement that we provided.")
#msg = "You don't need to change the code for the print statement."
#test_function("print", index=2, incorrect_msg=msg,  not_called_msg=msg)
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:3319f86744
## Get Thursday's weather forecast
From now on, we will work with a list of weather forecast from Monday to Sunday. Use the index feature of list objects to get the forecast for Thursday.

*** =instructions
- Assign the fourth element of the list `temp` to the variable `temp_Th`.
- Hit "submit answer" to print the result.

*** =hint
- The syntax to get the ith element of a list is `list[i]`. Remember the index of a list starts with 0.
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
temp = [29, 30, 35, 36, 32, 31, 29]
```

*** =sample_code
```{python}
# Find the fourth element of temp: temp_Th
temp_Th = temp[3]

# Print the temperature
print(temp_Th)

```

*** =solution
```{python}
# Find the fourth element of temp: temp_Th
temp_Th = temp[3]

# Print the temperature
print(temp_Th)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("Ethan_height")
#msg = "You don't need to change the code for the print statement."
#test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:1723f19db3
## Getting next week's weather forecast

Recall that a list itself can be an element in another list, and when we have list of lists, we can select any list-within-list just as we select any normal element. Now, the list `three_weeks_temp` contains three lists, each representing the weather forecast of a week starting from this one. Select next week's forecast and assign it to the variable `next_week_temp`.

*** =instructions
- Assign the second element of `three_weeks_temp` to `next_week_temp`.
- Hit "submit answer" to print `next_week_temp`.

*** =hint
- Use `list[i]` to select the ith element in a list.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
three_weeks_temp =[[29,30,28,25,29,31,31], [32, 30, 27, 25, 26, 25, 27], [19, 28, 30, 29, 32, 33, 32]]
```

*** =sample_code
```{python}
# Get a list of next week's weather: next_week_temp
next_week_temp = three_weeks_temp[1]

# Print the result
print(next_week_temp)

```

*** =solution
```{python}
# Get a list of next week's weather: next_week_temp
next_week_temp = three_weeks_temp[1]

# Print the result
print(next_week_temp)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
# test_object("weight")
# test_object("height")
# msg = "You don't need to change the code for the print statement."
# test_function("print", incorrect_msg=msg,  not_called_msg=msg)
# test_function_v2("print", params=["*objects"], incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")

```


--- type:NormalExercise lang:python xp:100 skills:1 key:3e74f114a8
## Finding the highest temperature
We can apply Python's built-in functions such as `max()` on list objects. With their help, we can easily find the highest temperature in the `next_week_temp` list we just created.


*** =instructions
- Find the highest temperature in `next_week_temp` and name it `high_temp`.
- Hit "submit answer" to print the highest temperature

*** =hint
- Pass `next_week_temp` as an argument to `max()` to find its maximum.
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
next_week_temp = [32, 30, 27, 25, 26, 25, 27]
```

*** =sample_code
```{python}
# Find the maximum in next_week_temp: high_temp
high_temp = max(next_week_temp)

# Print the result
print(high_temp)

```

*** =solution
```{python}
# Find the maximum in next_week_temp: high_temp
high_temp = max(next_week_temp)

# Print the result
print(high_temp)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_function("max")
#test_object("max_height")
#test_function("min")
#test_object("min_height")
#msg = "You don't need to change the code for the print statement."
#test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:e115d724c0
## Slicing the list
Due to an unexpected storm coming on Friday next week, we need to adjust the temperature prediction from that day on. Get rid of the original predictions for Friday to Sunday by slicing the list.

*** =instructions
- Slice the first four elements of the list `next_week_temp` and save it to `four_days_temp`.
- Hit "submit answer" to print out the result.

*** =hint
- Use `list[a:b]` to get a slice of the list from `a` to `b` (including `a` but not `b`), or `list[:a]` to get a slice from the beginning to `a` (not including `a`).
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
next_week_temp = [32, 30, 27, 25, 26, 25, 27]
```

*** =sample_code
```{python}
# take a slice of the next_week_temp list from beginning to the fourth element: four_days_temp
four_days_temp = next_week_temp[:4]

# Print out the resulting string
print(four_days_temp)

```

*** =solution
```{python}
# take a slice of the next_week_temp list from beginning to the fourth element: four_days_temp
four_days_temp = next_week_temp[:4]

# Print out the resulting string
print(four_days_temp)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("new_height")
#msg = "You don't need to change the code for the print statement."
#test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```



--- type:NormalExercise lang:python xp:100 skills:1 key:c91a8bede7
## Adding more records
The weather station has generated new predictions: Friday 23 degrees, Saturday 22 degrees, Sunday 24 degrees. Create a list from these predictions and add it to `four_days_temp`, which will now be an accurate forecast.  


*** =instructions
- Add the two temperature lists and store the new list in `next_week_temp`.

*** =hint
- You can just use `+` to add two lists.

*** =pre_exercise_code
```{python}
four_days_temp = [32, 30, 27, 25]
```

*** =sample_code
```{python}
# Create a list from the three new daily forecasts: temp_update
temp_update = [23, 22, 24]

# Add four_days_temp and temp_update: next_week_temp
next_week_temp = four_days_temp + temp_update

# Print the resulting list
print(next_week_temp)

```

*** =solution
```{python}
# Create a list from the three new daily forecasts: temp_update
temp_update = [23, 22, 24]

# Add four_days_temp and temp_update: next_week_temp
next_week_temp = four_days_temp + temp_update

# Print the resulting list
print(next_week_temp)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("complete_height")
#msg = "You don't need to change the code for the print statement."
#test_function_v2("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:6569731b94
## Updating a record
To complete our task of updating weather forecasts, we have learned a more efficient way: directly changing elements of a list. In this exercise, change the second last element of `forecast` to the value 23. We do not know how long the list `forecast` is.

*** =instructions
- Assign the value 23 to the second last element in the `forecast` list.

*** =hint
- Use `list[-i]` to call the ith last element of a list.

*** =pre_exercise_code
```{python}
forecast = [32, 31,28]
```

*** =sample_code
```{python}
# Update the second last element of forecast
forecast[-2] = 23

# Print out the updated list
print(forecast)

```

*** =solution
```{python}
# Update the second last element of forecast
forecast[-2] = 23

# Print out the updated list
print(forecast)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("complete_height")
#msg = "You don't need to change the code for the print statement."
#test_function_v2("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```
--- type:NormalExercise lang:python xp:100 skills:1 key:16955fff5b
## Converting the unit of weather forecast
Now that we have an accurate forecast of next week's weather, we will convert it to Fahrenheit. We will start with Wednesday's forecast in `next_week_temp` and convert it using the code you wrote.  

*** =instructions
- Select Wednesday's forecast and save it to `cel`.
- Run the rest of the code by clicking "submit answer" and see the result.

*** =pre_exercise_code
```{python}
next_week_temp = [32, 30, 27, 25, 23, 22, 24]
```

*** =sample_code
```{python}
# Select Wednesday's forecast: cel
cel = next_week_temp[2]

# Convert cel to Fahrenheit
fah = cel*(9/5)+32

# Print the result
print(fah)

```

*** =solution
```{python}
# Select Wednesday's forecast: cel
cel = next_week_temp[2]

# Convert cel to Fahrenheit
fah = cel*(9/5)+32

# Print the result
print(fah)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#test_object("Ethan_height")
#test_object("Ethan_weight")
#test_object("Ethan_BMI")
#test_function("print")

success_msg("Great work!")
```



--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3f0171461c
## Rounding and Counting
Which pair of commands round Wednesday's temperature (stored as `fah`) to an integer and count the total number of records in `next_week_temp`, respectively?

*** =instructions
- `round(fah)`
`count(next_week_temp)`
- `fah.round()`
`next_week_temp.count()`
- `round(fah)`
`next_week_temp.count()`
- `fah.round()`
`count(next_week_temp)`

*** =hint
- Destinguish between built-in functions and object-specific methods.

*** =pre_exercise_code
```{python}
fah = 80.6
next_week_temp = [32, 30, 27, 25, 23, 22, 24]
```

*** =sct
```{python}
msg1 = """`count` is a method specific to the list object."""

msg2 = """`round` is a built-in function in Python."""

msg3 = """Yes!"""

msg4 = """`count` is a method specific to the list objecgt."""

test_mc(3, [msg1, msg2, msg3, msg4])
```

--- type:NormalExercise lang:python xp:100 skills:1 key:ab4b93f572
## Converting all records to Fahrenheit
Create an empty list named `temp_fah`. Then use a for loop to go through every record in `next_week_temp`, convert it to Fahrenheit, and append the results to `temp_fah`.

*** =instructions
- Create an empty list named `temp_fah`.
- Use a for loop to go through all records in `next_week_temp`.
- Convert the temperature to Fahrenheit and append it to `temp_fah`.


*** =hint
- You can create an empty list with `[]`.
- Loop over each element in `next_week_temp`.
- Use `list.append()` to add a new element to a list.

*** =pre_exercise_code
```{python}
next_week_temp = [32, 30, 27, 25, 23, 22, 24]
```

*** =sample_code
```{python}
# Create an empty list: temp_fah
temp_fah = []

# Loop over all records
for cel in next_week_temp:
    fah = cel *(9/5)+32
    # Add fah to temp_fah
    temp_fah.append(fah)

# Print temp_fah
print(temp_fah)

```

*** =solution
```{python}
# Create an empty list: temp_fah
temp_fah = []

# Loop over all records
for cel in next_week_temp:
    fah = cel *(9/5)+32
    # Add fah to temp_fah
    temp_fah.append(fah)

# Print temp_fah
print(temp_fah)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
# test_object("BMI")
# test_function("print")

success_msg("Great work!")
```
