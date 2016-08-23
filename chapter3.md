---
title       : Analyzing World Cup Performance (1)
description : In this chapter, you will use Numpy and matplotlib to create plots analyzing different teams' performance in world cup.

--- type:MultipleChoiceExercise lang:python xp:50 skills:2 key:0bb15c454e
## List and array
Operators such as `+` and  `-` behave differently on lists and numpy arrays. Which of the following calculations is correct?

*** =instructions
- `[1, 3, 5] + [2, 4, 6] = [3, 7, 11]`
- `[1, 3, 5] * 3 = [1, 3, 5, 1, 3, 5, 1, 3, 5]`
- `np.array([1, 3, 5]) + np.array([2, 4, 6]) = array([1, 3, 5, 2, 4, 6])`
- `np.array([1, 3, 5]) * 3 = array([1, 3, 5, 1, 3, 5, 1, 3, 5])`

*** =hint
Review Chapter 4, Exercise 6 in "Intro to Python for Data Science" for the differences between list and arrays.

*** =pre_exercise_code
```{python}
# pec
```

*** =sct
```{python}
msg1 = """Adding two lists will append the latter to the former."""

msg2 = """Yes!"""

msg3 = """Adding two arrays with the same length will add the elements with the same index."""

msg4 = """Multiplying an array with a number will multiply each element in the array with that number."""

test_mc(2, [msg1, msg2, msg3, msg4])
``````

--- type:NormalExercise lang:python xp:100 skills:2 key:55962df285
## Comparing arrays
Countries from six continents participate in the FIFA World Cup: Africa, Asia, CONCACAF, Europe, Oceania, and South America. We want to compare the performance of CONCACAF countries and African countries by looking at the average goal difference (goals for a team - goals against a team) when a team from these two continents plays against a team from another continent. To do this, we have created two lists for CONCACAF's and Africa's performance, where the goal difference between a continent against itself is set to 0. Transform these lists to arrays and compare if Africa has a higher goal difference than CONCACAF when facing each of the six continents.

*** =instructions
- Transform the two lists to arrays.
- Create an array of booleans to represent whether African outperforms CONCACAF when facing each continent.
- Print the resulting array.

*** =hint
- Use `np.array()` to transform a list to an array.
- You can compare two arrays by using `>`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
```

*** =sample_code
```{python}
#Import numpy as np
import numpy as np

# Create arrays to represent the average GF and GA of CONCACAF and African teams
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]

# Transform the lists to arrays: CONCACAF_np, Africa_np
Africa_np = np.array(Africa)
CONCACAF_np = np.array(CONCACAF)

# Compare if CONCACAF outperforms Africa in each field: AC
AC = CONCACAF_np>Africa_np

# Print AC
print(AC)

```

*** =solution
```{python}
#Import numpy as np
import numpy as np

# Create arrays to represent the average GF and GA of CONCACAF and African teams
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]

# Transform the lists to arrays: CONCACAF_np, Africa_np
Africa_np = np.array(Africa)
CONCACAF_np = np.array(CONCACAF)

# Compare if CONCACAF outperforms Africa in each field: AC
AC = CONCACAF_np>Africa_np

# Print AC
print(AC)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:bb1f7fa08f
## Creating a 2D array
We have created lists for all continents that represent their goal difference against each other. Now, put them all together in a 2D array, and find the type and shape of the resulting array.

*** =instructions
- Create a 2D array that represents the six continents' goal differences against each other.
- Print the type of the resulting array.
- Print the shape of the resulting array.

*** =hint
- Create a 2D array from a list that contains all the pre-defined lists.
- Use `type()` to find the type of an object.
- Use the `shape` attribute to find the shape of an array.

*** =pre_exercise_code
```{python}
# pec
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Create arrays that represent the six continents' performance
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a 2D array from the lists: world_cup
world_cup = np.array([Africa, Asia, CONCACAF, Europe, Oceania, SouthAmerica])

# Print the type of world_cup
print(type(world_cup))

# Print the shape of world_cup
print(world_cup.shape)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Create arrays that represent the six continents' performance
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a 2D array from the lists: world_cup
world_cup = np.array([Africa, Asia, CONCACAF, Europe, Oceania, SouthAmerica])

# Print the type of world_cup
print(type(world_cup))

# Print the shape of world_cup
print(world_cup.shape)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:2 key:810927b295
## Subsetting 2D array
If our data is correct, then the column representing each continent's goal difference against Europe should be the opposite of Europe's goal difference against each continent. To check if this is the case, subset the 4th column and the 4th line of the 2D array we just created, both representing Europe, and print out the results.

*** =instructions
- Subset the 4th column of `world_cup`.
- Subste the 4th row of `world_cup`.
- Print the results.

*** =hint
- Use [:,i] to subset the ith column of a 2D array. Remember in numpy arrays, index starts with 0.
- Use [i,:] to subset the ith row of a 2D array. Remember in numpy arrays, index starts with 0.
- You don't need to chang the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
# Import numpy as np
import numpy as np

# Create arrays that represent the six continents' performance
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a 2D array from the lists: world_cup
world_cup = np.array([Africa, Asia, CONCACAF, Europe, Oceania, SouthAmerica])
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Subset the 4th column of world_cup: Europe_col
Europe_col = world_cup[:,3]

# Subset the 4th row of world_cup: Europe_row
Europe_row = world_cup[3,:]

# Print the shape of world_cup
print(Europe_col, Europe_row)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Subset the 4th column of world_cup: Europe_col
Europe_col = world_cup[:,3]

# Subset the 4th row of world_cup: Europe_row
Europe_row = world_cup[3,:]

# Print the shape of world_cup
print(Europe_col, Europe_row)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:89ce8f8518
## Calculations with 2D arrays
Suppose that after 2018 Russian World Cup, there are some updates to our data that are stored in the 2D array `update`. Add `update` to `world_cup` to get the up-to-date information on goal differences between continents. Then multiply all the records by 10 to get rid of the decimal point.

*** =instructions
- Add `update` to `world_cup` and save the resulting array as `world_cup_2018`.
- Multiply `world_cup_2018` by 10 and save the resulting resulting array as `world_cup_2018_10x`.
- Print `world_cup_2018_10x`.

*** =hint
- You can add 2D arrays simply by using `+`.
- You can multiply a 2D array by a number simply by using `*`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
# Import numpy as np
import numpy as np

# Create arrays that represent the six continents' performance
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a 2D array from the lists: world_cup
world_cup = np.array([Africa, Asia, CONCACAF, Europe, Oceania, SouthAmerica])

# Create update
update = np.array([[0, 0.1, 0, 0.1, -0.2, 0.1],[-0.1, 0, 0.1, -0.1, 0, 0], [0, -0.1, 0, 0.1, 0.1, -0.2], [-0.1, 0.1, -0.1, 0, 0, 0.1], [0.2, 0, -0.1, 0, 0, -0.1],[-0.1, 0, 0.2, -0.1, 0.1, 0]])
```

*** =sample_code
```{python}
# Add world_cup and update: world_cup_2018
world_cup_2018 = world_cup + update

# Multiply world_cup_2018 by 10: world_cup_2018_10x
world_cup_2018_10x = world_cup_2018 *10

# Print world_cup_2018_10x
print(world_cup_2018_10x)

```

*** =solution
```{python}
# Add world_cup and update: world_cup_2018
world_cup_2018 = world_cup + update

# Multiply world_cup_2018 by 10: world_cup_2018_10x
world_cup_2018_10x = world_cup_2018 *10

# Print world_cup_2018_10x
print(world_cup_2018_10x)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:df963fedca
## Create a dictionary to store continent profile

The biggest inconvenience in our 2D array is that it doesn't show what the data is supposed to denote. For instance, when we see `world_cup_2018[1,2] = 0.1`, it's not intuitive which two continents this is about. This is a case when a dictionary, with both keys and values, is a more intuitive way to store our data. So let's use the continent list and Africa's goal difference list to create a dictionary for Africa's goal difference dictionary.

*** =instructions
- With the strings in `continents` and the numbers in `Africa`, create a dictionary called `AF` with 5 key:value pairs (we will ignore Africa's goal difference against itself).
- Print out the dictionary.

*** =hint
- You can either create the dictionary manually or use a for loop.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
```

*** =sample_code
```{python}
# Lists of continents and Africa's goal differences against them
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']
Africa = [0, 0, 0.1, -0.6, 0, -1.1]

# Use the lists to create a dictionary: AF
AF = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}

# Print the dictionary
print(AF)

```

*** =solution
```{python}
# Lists of continents and Africa's goal differences against them
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']
Africa = [0, 0, 0.1, -0.6, 0, -1.1]

# Use the lists to create a dictionary: AF
AF = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}

# Print the dictionary
print(AF)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:fd50133b2a
## Accessing Africa's profile
Check out what continents are in `AF`, and find the sum of Africa's goal differences against Europe and against South America.

*** =instructions
- Print the keys in the dictionary `AF`.
- Print the sum of the values belonging to `Europe` and `SouthAmerica`.

*** =hint
- Use `keys()` method to find all the keys in a dictionary
- Use the command `dict[key]` to find the value of a key.

*** =pre_exercise_code
```{python}
# pec
AF = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}

```

*** =sample_code
```{python}
# Print the keys in the dictionary AF
print(AF.keys())

# Print the sum of Europe and SouthAmerica
print(AF['Europe'] + AF['SouthAmerica'])

```

*** =solution
```{python}
# Print the keys in the dictionary AF
print(AF.keys())

# Print the sum of Europe and SouthAmerica
print(AF['Europe'] + AF['SouthAmerica'])

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:d75bdf4908
## Updating profile

Suppose that our calculation of Africa's goal difference against South America has been wrong, and it should be  `1.0`. Update the value belonging to the `SouthAmerica` key to reflect the change. Also, it is unnecessary to include Africa's goal difference against itself in the `AF` dictionary, so let's remove it.

*** =instructions
- Update the value belonging to the `SouthAmerica` key to `1.0`.
- Remove the key:value pair for `Africa`.
- Print the updated dictionary.

*** =hint
- Change the value of `SouthAmerica` by using `AF['SouthAmerica']`.
- Remove the key:value pair for `Africa` by using the `del()` method.
- You don't need to change the code for the `print()` statement that we provided.


*** =pre_exercise_code
```{python}
# pec
AF = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}

```

*** =sample_code
```{python}
# Update the value of SouthAmerica
AF['SouthAmerica'] = 1.0

# Delete the key:value pair for Africa
del(AF['Africa'])

# Print the updated dictionary
print(AF)

```

*** =solution
```{python}
# Update the value of SouthAmerica
AF['SouthAmerica'] = 1.0

# Delete the key:value pair for Africa
del(AF['Africa'])

# Print the updated dictionary
print(AF)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:2794080a8a
## Profiles of all continents
We have created a dictionary named `world_cup` for all continents' goal difference profiles, where each continent's profile is itself a dictionary. We will now do some manipulations on this dictionary.

*** =instructions
- Print out CONCACAF's goal difference against Asia.
- Create a dictionary named `data`. Add the names of the six continents in the World Cup as keys, and set all values to 0.
- Add a new key:value pair to `world_cup`: the key is `AN` (for Antarctica) and the value is `data` —— Antarctica has never participated in the World Cup yet, but who knows what will happen in the future!
- Print the updated `world_cup` dictionary.

*** =hint
- Use two square brackets to first select `CONCACAF` in `world_cup`, then select `AS` in
`CONCACAF`.
- Manually create a dictionary by typing in all the key:value pairs.
- Add a new key:value pair to a dictionary by `dict[key] = value`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
```

*** =sample_code
```{python}
world_cup = {'AF': { 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}, 'AS': {'Africa': 0, 'CONCACAF': -0.8, 'Europe': -1.5, 'Oceania': -0.5, 'SouthAmerica': -1.9}, 'CONCACAF': {'Africa': -0.1, 'Asia': 0.8, 'Europe': -1.1, 'Oceania': -1.5, 'SouthAmerica': -1.4}, 'EU': {'Africa': 0.6, 'Asia': 1.5, 'CONCACAF': 1.1, 'Oceania': 1, 'SouthAmerica': -0.1}, 'OC': {'Africa': 0, 'Asia': 0.5, 'CONCACAF': 1.5, 'Europe': -1, 'SouthAmerica': -0.3}, 'SA': {'Africa': 1.1, 'Asia': 1.9, 'CONCACAF': 1.4, 'Europe': 0.1, 'Oceania': 0.3}}

# Print CONCACAF's goal difference against Asia
print(world_cup['CONCACAF']['Asia'])

# Create a new dictionary: data
data = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0, 'Europe': 0, 'Oceania': 0, 'SouthAmerica': 0}

# Add data to world_cup
world_cup['AN'] = data

```

*** =solution
```{python}
world_cup = {'AF': { 'Asia': 0, 'CONCACAF': 0.1, 'Europe': -0.6, 'Oceania': 0, 'SouthAmerica': -1.1}, 'AS': {'Africa': 0, 'CONCACAF': -0.8, 'Europe': -1.5, 'Oceania': -0.5, 'SouthAmerica': -1.9}, 'CONCACAF': {'Africa': -0.1, 'Asia': 0.8, 'Europe': -1.1, 'Oceania': -1.5, 'SouthAmerica': -1.4}, 'EU': {'Africa': 0.6, 'Asia': 1.5, 'CONCACAF': 1.1, 'Oceania': 1, 'SouthAmerica': -0.1}, 'OC': {'Africa': 0, 'Asia': 0.5, 'CONCACAF': 1.5, 'Europe': -1, 'SouthAmerica': -0.3}, 'SA': {'Africa': 1.1, 'Asia': 1.9, 'CONCACAF': 1.4, 'Europe': 0.1, 'Oceania': 0.3}}

# Print CONCACAF's goal difference against Asia
print(world_cup['CONCACAF']['Asia'])

# Create a new dictionary: data
data = {'Africa': 0, 'Asia': 0, 'CONCACAF': 0, 'Europe': 0, 'Oceania': 0, 'SouthAmerica': 0}

# Add data to world_cup
world_cup['AN'] = data

```

*** =sct
```{python}
success_msg("Great work!")
```
