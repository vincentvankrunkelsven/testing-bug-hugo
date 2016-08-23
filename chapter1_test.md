---
title       : Calculating BMI
description : In this chapter you will Practice the basic functionalities of Python, including calculations, variable assignments, built-in functions and methods. We will also work on the manipulation of string objects. Let's get started!
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf


--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:8c8181cc6b
## What is BMI?

Body mass index (BMI) is a measure of body fat based on height and weight that applies to adult men and women. It equals weight (in kilograms) divided by the square of height (in meters). A BMI is normal when it is between 18.5 and 24.9. Now, use Python to calculate the BMI of someone whose weight is 65kg and whose height is 1.78m.

*** =instructions
- 19.98
- 20.52
- 22.46

*** =hint
- You can use `**2` to calculate the square of a number.

*** =pre_exercise_code
```{python}

```

*** =sct
```{python}
msg1 = """Check your calculation."""

msg2 = """Yes!"""

msg3 = """Check your calculation."""

test_mc(2, [msg1, msg2, msg3])
```

--- type:NormalExercise lang:python xp:50 skills:1 key:514818b19a
## Using variables to store values

A lot of times we need to save the values and pass them to other calculations. In such cases we can assign values to variables. In this exercise, we already assigned a person's weight to the variable `weight` and his height to the variable `height`. Use these variables to calculate his BMI and save it to the variable `BMI`.

*** =instructions
- Calculate the person's BMI and save it to the variable BMI.
- Find the type of BMI and print it.
- Hit "submit answer" to print the result.

*** =hint
- In your calculations, you can use variables as if they are numbers.
- Use `type(a)` to find the type of the variable `a`.
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
weight = 68
height = 1.73
```

*** =sample_code
```{python}
# Calculate BMI: BMI


# Print the type of BMI
print(____)

# Print the result
print(BMI)

```

*** =solution
```{python}
# Calculate BMI: BMI
BMI = weight/height**2

# Print the type of BMI
print(type(BMI))

# Print the result
print(BMI)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("BMI")
test_function("print", index=1, incorrect_msg="Did you find the type of BMI?", not_called_msg="You don't need to change the code for the print statement that we provided.")
msg = "You don't need to change the code for the print statement."
test_function("print", index=2, incorrect_msg=msg,  not_called_msg=msg)
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:3319f86744
## Get Ethan's height
From now on, we will work with lists of height and weight. To begin with, we have a list that represents the height of students in a class. We know that the height of Ethan, one of the students, is the fourth element in this list. Get his height using index.

*** =instructions
- Assign the fourth element of the list `height` to the variable `Ethan_height`.
- Hit "submit answer" to print the result.

*** =hint
- The syntax to get the ith element of a list is `list[i]`. Remember the index of a list starts with 0.
- You don't need to change the code for the `print()` statement.

*** =pre_exercise_code
```{python}
height = [1.74, 1.58, 1.69, 1.75, 1.87]
```

*** =sample_code
```{python}
# Find the fourth element of height: Ethan_height


# Print Ethan's height
print(Ethan_height)

```

*** =solution
```{python}
# Find the fourth element of height: Ethan_height
Ethan_height = height[3]

# Print Ethan's height
print(Ethan_height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("Ethan_height")
msg = "You don't need to change the code for the print statement."
test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:1723f19db3
## Separating Weights and Heights

Recall that a list itself can be an element in another list, and when we have list of lists, we can select any list-within-list just as we select any normal element. Now, the list `class_profile` contains two lists, one that is the weight of the whole class and another that is their height. Select and assign these two lists to `weight` and `height`, respectively.

*** =instructions
- Assign the first element of `class_profile` to `weight` and its second element to `height`.
- Hit "submit answer" to print `weight` and `height`.

*** =hint
- Use `class[i]` to select the ith element in the list `class`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
class_profile = [[53, 48, 60, 65, 68],[1.74, 1.58, 1.69, 1.75, 1.87]]
```

*** =sample_code
```{python}
# Get a list of weight from class_profile: weight


# Get a list of height from class_profile: height


# Print the result
print(weight, height)

```

*** =solution
```{python}
# Get a list of weight from class_profile: weight
weight = class_profile[0]

# Get a list of height from class_profile: height
height = class_profile[1]

# Print the result
print(weight, height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("weight")
test_object("height")
msg = "You don't need to change the code for the print statement."
test_function("print", incorrect_msg=msg,  not_called_msg=msg)
#test_function_v2("print", params=["weight", "height"], incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")

```


--- type:NormalExercise lang:python xp:100 skills:1 key:3e74f114a8
## Finding the Maximum and Minimum
We can apply Python's built-in functions such as `max()` and `min()` on list objects. With their help, we can easily find the maximum and minimum height in the `height` list we just created.


*** =instructions
- Find the maximum in `height`.
- Find the minimum in `height`.

*** =hint
- Pass `height` as an argument to `max()` to find its maximum.
- Pass `height` as an argument to `min()` to find its minimum.

*** =pre_exercise_code
```{python}
height = [1.74, 1.58, 1.69, 1.75, 1.87]
```

*** =sample_code
```{python}
# Find the maximum in height: max_height


# Find the minimum in height: min_height


# Print the result
print(max_height, min_height)

```

*** =solution
```{python}
# Find the maximum in height: max_height
max_height = max(height)

# Find the minimum in height: min_height
min_height = min(height)

# Print the result
print(max_height, min_height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_function("max")
test_object("max_height")
test_function("min")
test_object("min_height")
msg = "You don't need to change the code for the print statement."
test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:e115d724c0
## Slicing a list
Ted has quited from the class. We have to take his height away from the `height` list. If he is the first student in the list, use list slicing to get a new height list.

*** =instructions
- Use list slicing to get a new height list `new_height`.

*** =hint
- Use `list[a:b]` to get a slice of the list from a to b, or  `list[a:]` to get a slice from a to the end.

*** =pre_exercise_code
```{python}
class = [1.74, 1.58, 1.69, 1.75, 1.87]
```

*** =sample_code
```{python}
# take a slice of the height list from the second element to the last one


# Print out the resulting string
print(new_height)

```

*** =solution
```{python}
# take a slice of the height list from the second element to the last one
new_height = height[1:]

# Print out the resulting string
print(new_height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("new_height")
msg = "You don't need to change the code for the print statement."
test_function("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```



--- type:NormalExercise lang:python xp:100 skills:1 key:c91a8bede7
## Adding more records
Now two students have transferred to the class we are profiling, and their heights are in the list `transfer_height`. Add this list with the `new_height` list.


*** =instructions
- Add the two height lists and store the new list in `complete_height`.

*** =hint
- You can just use `+` to add two lists.

*** =pre_exercise_code
```{python}
transfer_height = [1.72, 1.68]
height = [1.58, 1.69, 1.75, 1.87]
```

*** =sample_code
```{python}
# Add the two height lists: complete_height


# Print the resulting list
print(complete_height)

```

*** =solution
```{python}
# Add the two height lists: complete_height
complete_height = height + transfer_height

# Print the resulting list
print(complete_height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("complete_height")
msg = "You don't need to change the code for the print statement."
test_function_v2("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1 key:6569731b94
## Updating a record
Ethan has grown to 1.81m, and his record in the `complete_height` list is no longer accurate. Replace his old height with his current height. His height is the third in the list.

*** =instructions
- Assign Ethan's current height to the third element in the `complete_height` list.

*** =hint
- Use `list[i]` to call the ith element of a list.

*** =pre_exercise_code
```{python}
complete_height = [1.58, 1.69, 1.75, 1.87, 1.72, 1.68]
```

*** =sample_code
```{python}
# Update Ethan's height


# Print out the resulting list
print(complete_height)

```

*** =solution
```{python}
# Update Ethan's height
complete_height[2] = 1.81

# Print out the resulting list
print(complete_height)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("complete_height")
msg = "You don't need to change the code for the print statement."
test_function_v2("print", incorrect_msg=msg,  not_called_msg=msg)

success_msg("Great work!")
```
--- type:NormalExercise lang:python xp:100 skills:1 key:16955fff5b
## Calculating Ethan's BMI
Select Ethan's height and weight from `complete_height` and `complete_weight`, both are up-to-date records, and calculate Ethan's BMI. His height and weight are the third elements in the two lists, respectively.

*** =instructions
- Assign Ethan's height to the variable `Ethan_height`.
- Assign Ethan's weight to the variable `Ethan_weight`.
- Hit `submit answer` to print Ethan's BMI

*** =hint
- Use `list[i]` to call the ith element of a list.
- Recall that the index of a list starts with 0.
- You don't need to change the code to calculate and print Ethan's BMI, which we provided.

*** =pre_exercise_code
```{python}
complete_height = [1.58, 1.69, 1.75, 1.87, 1.72, 1.68]
complete_weight = [48, 60, 65, 68, 56, 53]
```

*** =sample_code
```{python}
# Get Ethan's height and weight from the list: Ethan_height, Ethan_weight



# Calculate Ethan's BMI
Ethan_BMI = Ethan_weight/Ethan_height**2

print(Ethan_BMI)

```

*** =solution
```{python}
# Get Ethan's height and weight from the list: Ethan_height, Ethan_weight
Ethan_height = complete_height[2]
Ethan_weight = complete_weight[2]

# Calculate Ethan's BMI
Ethan_BMI = Ethan_weight/Ethan_height**2

print(Ethan_BMI)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("Ethan_height")
test_object("Ethan_weight")
test_object("Ethan_BMI")
test_function("print")

success_msg("Great work!")
```



--- type:MultipleChoiceExercise lang:python xp:100 skills:1 key:3f0171461c
## Rounding and Counting
Which pair of commands round Ethan's BMI to an integer and count the total number of records in `complete_weight`, respectively?

*** =instructions
- `round(Ethan_BMI)`
`count(complete_weight)`
- `Ethan_BMI.round()`
`complete_weight.count()`
- `round(Ethan_BMI)`
`complete_weight.count()`
- `Ethan_BMI.round()`
`count(complete_weight)`

*** =hint
- Destinguish and between built-in functions and object-specific methods.

*** =pre_exercise_code
```{python}
Ethan_BMI = 21.224489795918366
complete_weight = [48, 60, 65, 68, 56, 53]
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
## Calculating everyone's BMI
Use a for loop to go through everyone's records in `complete_height` and `complete_weight` and calculate his or her BMI. Append the results to the list `BMI`.

*** =instructions
- Create an empty list named `BMI`.
- Use a for loop to go through all records.
- Calculate BMI and add the result to `BMI`.


*** =hint
- You can create an empty list with `[]`.
- You can loop over the index of `complete_height` and `complete_weight`.
- Use `list.append()` to add a new element to a list.

*** =pre_exercise_code
```{python}
complete_height = [1.58, 1.69, 1.75, 1.87, 1.72, 1.68]
complete_weight = [48, 60, 65, 68, 56, 53]
```

*** =sample_code
```{python}
# Create an empty list: BMI


# Loop over everyone's  records
for ____ in ____:
    weight = ____
    height = ____
    result = weight/height**2
    # Add result to the BMI list


# Print BMI
print(BMI)

```

*** =solution
```{python}
# Create an empty list: BMI
BMI = []

# Loop over everyone's  records
for i in range(len(complete_weight)):
    weight = complete_weight[i]
    height = complete_height[i]
    result = weight/height**2
    # Add result to the BMI list
    BMI.append(result)

# Print BMI
print(BMI)

```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
test_object("BMI")
test_function("print")

success_msg("Great work!")
```
