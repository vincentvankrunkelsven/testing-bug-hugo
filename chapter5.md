---
title       : Correlation Between Female Literacy and Fertility
description : In this chapter, we will use logic, control flow, filtering, and loops to manipulate the dataset of female literacy and fertility and find their relationship.

--- type:NormalExercise lang:python xp:100 skills:2 key:9363d8730c
## comparison operator
We have created a numpy array "top10lit_fert" that includes the fertility data in the 10 countries with the highest literacy rates. We also know that the average fertility rate of  a country is 2.88. Use comparison operators to create another array "top10lit_fert_bool" to indicate whether each of these countries' fertility rate is higher than 2.88.


*** =instructions
- Import numpy as np.
- Create an array "top10lit_fert_bool" to indicate whether each country in `top10lit_fert` has a fertility rate higher than 2.88.
- Print `top10lit_fert_bool`.

*** =hint
- The command to import `x` as `y` is `import x as y`.
- Use `top10lit_fert>2.88` to create `top10lit_fert_bool`.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}
import numpy as np
top10lit_fert = np.array([1.885, 1.836, 1.854, 1.693, 1.426, 1.361, 1.281,1.582,1.367,1.393])
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Create an array to compare data in top10lit_fert and 2.88: top10lit_fert_bool
top10lit_fert_bool = top10lit_fert>2.88

# Print top10lit_fert_bool
print(top10lit_fert_bool)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Create an array to compare data in `top10lit_fert` and 2.88: top10lit_fert_bool
top10lit_fert_bool = top10lit_fert>2.88

# Print top10lit_fert_bool
print(top10lit_fert_bool)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:ab7f2d514d
## Compare Arrays
The ten countries with the highest female literacy in the world all have less than average fertility rates. This seems to suggest a strong correlation. But what about the other end of the spectrum? Compare `top10lit_fert` to `bot10lit_fert`, the fertility data of the 10 countries with the lowest literacy rates, and see what we will get.

*** =instructions
- Import numpy as np.
- Create an array `topbot10_bool` to indicate whether each country in `top10lit_fert` has a fertility rate higher than the corresponding country in `bot10lit_fert`.
- Print `topbot10_bool`.

*** =hint
- The command to import `x` as `y` is `import x as y`.
- Use `top10lit_fert>bot10lit_fert` to create `topbot10_bool`.
- You don't need to change the code for the print statement that we provided.

*** =pre_exercise_code
```{python}
import numpy as np
top10lit_fert = np.array([1.885, 1.836, 1.854, 1.693, 1.426, 1.361, 1.281,1.582,1.367,1.393])
bot10lit_fert = np.array([6.505, 7.069, 5.405, 5.841, 6.081, 5.211, 5.329, 5.378, 5.165, 4.89])
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Create an array to compare data in top10lit_fert and bot10lit_fert: topbot10_bool
topbot10_bool = top10lit_fert>bot10lit_fert

# Print top10lit_fert_bool
print(topbot10_bool)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Create an array to compare data in top10lit_fert and bot10lit_fert: topbot10_bool
topbot10_bool = top10lit_fert>bot10lit_fert

# Print top10lit_fert_bool
print(topbot10_bool)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:92dad3df57
## Boolean Operators on Arrays
Now let's look at the literacy and fertility data of 10 countries that we have selected randomly. Use the boolean operator "and" to find out how many of them have a literacy rate higher than 70, and a fertility rate higher than 2.88. Store the result as booleans in `random_bool`.

*** =instructions
- Create an array named `random_bool` to store whether each of the 10 countries has a literacy rate higher than 70 and a fertility rate higher than 2.88.
- Print `random_bool`.

*** =hint
- Use `np.logical_and()` to create `random_bool`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Create arrays for literacy rates and fertility rates of 10 random countries
random_lit = np.array([95.9, 99, 26.4, 93.1, 89.2, 90, 89.1, 79.5, 44.3, 81.4])
randomm_fert = np.array([1.212, 1.45, 5.329, 2.152, 2.281, 2.36, 2.308, 3.883, 4.514, 2.295])

# Create an array to store if each country has a literacy rate higher than 70 and fertility rate higher than 2.88
random_bool = np.logical_and(random_lit>70, randomm_fert>2.88)

# Print random_bool
print(random_bool)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Create arrays for literacy rates and fertility rates of 10 random countries
random_lit = np.array([95.9, 99, 26.4, 93.1, 89.2, 90, 89.1, 79.5, 44.3, 81.4])
randomm_fert = np.array([1.212, 1.45, 5.329, 2.152, 2.281, 2.36, 2.308, 3.883, 4.514, 2.295])

# Create an array to store if each country has a literacy rate higher than 70 and fertility rate higher than 2.88
random_bool = np.logical_and(random_lit>70, randomm_fert>2.88)

# Print random_bool
print(random_bool)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:8f38ec0054
## Looping over lists
After looking at samples, let's look at the data of all the 162 countries that we have data of. Loop over all the countries in `all_lit` list and `all_fert` list, and create a boolean list to indicate what countries have a literacy rates higher than 70 in `all_lit` and fertility rates higher than 2.88 in `all_fert`.

*** =instructions
- Initiate an empty list named `results`.
- Loop over the index of `all_lit` and `all_fert`, whose length is 162.
- For each index, test whether the corresponding data in `all_lit` is higher than 70 and the data in `all_fert` is higher than 2.88. Append the result to `results`.
- Print `results`.

*** =hint
- Use `[]` to create an empty list `results`.
- Create a for loop to loop over `range(162)`.
- Use boolean operator `and` and comparison oeprator `>` to test if the literacy rate is higher than 70 and the fertility rate is higher than 2.88.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
import pandas as pd
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_1397/datasets/female_literacy_fertility.csv')

all_lit = df["female literacy"].tolist()
all_fert = df["fertility"].tolist()
```

*** =sample_code
```{python}
# Initiate results
results = []

# Loop over the index of both lists
for i in range(162):
    # find out if a country's literacy rate is higher than 70, and fertility rate higher than 2.88: bool
    bool=all_lit[i] > 70 and all_fert[i] > 2.88
    # Append bool to results
    results.append(bool)

# Print results
print(results)

```

*** =solution
```{python}
# Initiate results
results = []

# Loop over the index of both lists
for i in range(162):
    # find out if a country's literacy rate is higher than 70, and fertility rate higher than 2.88: bool
    bool=all_lit[i] > 70 and all_fert[i] > 2.88
    # Append bool to results
    results.append(bool)

# Print results
print(results)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:ba682dbd97
## Looping over dictionaries and numpy arrays
From previous exercises, it seemed pretty likely that high female literacy rates is correlated to low fertility rates. However, this doesn't necessarily suggest a causal relation between the two. For instance, maybe they are both influenced by the population of a country, or maybe countries in certain regions value both high literacy and low fertility. In this exercise, let's take a brief look at these previously unconsidered factors. We have already imported numpy as np.

*** =instructions
- Loop over the dictionary `top10_lit`, where the keys are the 10 countries with the highest female literacy rates, and the values are their continents. print out the continents.
- Loop over `top10_pop`, a numpy array of these 10 countries' populations, and print if they are larger than 40,687,080, the average population of all the 162 countires.


*** =hint
- Use `for key, value in dict.items()` to loop over the key:value pairs of a dictionary `dict`.
- Use `for x in np.nditer(my_array)` to loop over the values in a numpy array `my_array`.

*** =pre_exercise_code
```{python}

```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Create the dicionary top10_lit and the numpy array top10_pop
top10_lit = {"Norway": "EUR", "Finland": "EUR", "Democratic People's Republic of Korea":"ASI", "Estonia": "EUR", "Latvia": "EUR", "Cuba":"LAT", "Slovenia": "EUR", "Lithuania": "EUR", "Georgia": "ASI", "Belarus": "EUR"}
top10_pop = np.array([47868212, 5313399, 23818753, 1340675, 2266094, 11204735, 2021316, 3358115, 4307011, 9680850])

# Loop over top10_lit and print the continents
for key, value in top10_lit.items():
    print(value)

# Loop over top10_pop and print
for x in np.nditer(top10_pop):
    print(x>40687080)


```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Create the dicionary top10_lit and the numpy array top10_pop
top10_lit = {"Norway": "EUR", "Finland": "EUR", "Democratic People's Republic of Korea":"ASI", "Estonia": "EUR", "Latvia": "EUR", "Cuba":"LAT", "Slovenia": "EUR", "Lithuania": "EUR", "Georgia": "ASI", "Belarus": "EUR"}
top10_pop = np.array([47868212, 5313399, 23818753, 1340675, 2266094, 11204735, 2021316, 3358115, 4307011, 9680850])

# Loop over top10_lit and print the continents
for key, value in top10_lit.items():
    print(value)

# Loop over top10_pop and print
for x in np.nditer(top10_pop):
    print(x>40687080)

```

*** =sct
```{python}
success_msg("It seems that countries with high female literacy rates are mostly in Europe and have small population. Maybe these two factors are related to their low fertility rates.")
```



--- type:NormalExercise lang:python xp:100 skills:2 key:4a679afcf8
## If...else...
You might have noticed that when we checked out the female literacy rates and fertility rates of ten random countries, the vast majority had fertility rates less than 2.88. The only two outliers, though, have really high fertility rates (3.883 and 4.514, respectively). This leads us to suspect that our average rate, 2.88, is heavily influenced by a handful countries with really high fertility rate, in which case it could have led to misleading results. To test this possibility, loop over `all_fert` again, and calculate the average fertility rate among countries where fertility rates are over 2.88, and those where fertility rates are below 2.88.

*** =instructions
- Initiate `high_fert_sum`, `low_fert_sum`, `high_fert_count`, and `low_fert_count`, all to 0.
- Loop over `all_fert` and use `if` and `else` to classify countreis by fertility rate.
- For each country where fertility rate is over 2.88, Increase `high_fert_sum` by its fertility rate and `high_fert_count` by 1. Otherwise, increase `low_fert_sum` by the country's fertility rate and  `low_fert_count` by 1.
- Divide `high_fert_sum` by `high_fert_count`, and `low_fert_sum` by `low_fert_count`. Print the result.

*** =hint
- Assign the value `0` to `high_fert_sum`, `low_fert_sum`, `high_fert_count`, and `low_fert_count`.
- Use a for loop to go through `all_fert`, and then use `if` and `else`.
- You cnan use `+=` to increase a variable's value by a number.
- Use math operators to do the calculations.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_1397/datasets/female_literacy_fertility.csv')

all_fert = df["fertility"].tolist()
```

*** =sample_code
```{python}
# Initiate high_fert_sum, low_fert_sum, high_fert_count, low_fert_count
high_fert_sum = 0
low_fert_sum = 0
high_fert_count = 0
low_fert_count = 0

# Loop over all_fert and classify countries by fertility rate
for x in all_fert:
    if x>2.88:
        high_fert_sum += x
        high_fert_count += 1
    else:
        low_fert_sum += x
        low_fert_count +=1

# Calculate and print the averages
print(high_fert_sum/high_fert_count, low_fert_sum/low_fert_count)


```

*** =solution
```{python}
# Initiate high_fert_sum, low_fert_sum, high_fert_count, low_fert_count
high_fert_sum = 0
low_fert_sum = 0
high_fert_count = 0
low_fert_count = 0

# Loop over all_fert and classify countries by fertility rate
for x in all_fert:
    if x>2.88:
        high_fert_sum += x
        high_fert_count += 1
    else:
        low_fert_sum += x
        low_fert_count +=1

# Calculate and print the averages
print(high_fert_sum/high_fert_count, low_fert_sum/low_fert_count)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:MultipleChoiceExercise lang:python xp:50 skills:2 key:4517b4a917
## Filtering DataFrame
While the countries with fertility rates lower than 2.88 are on average about 1 lower, those with fertility rates higher than 2.88 are on average about 2 higher. This is indeed an interesting phenomenon, and it would be cool to get more information on these countries! In your IPython Shell we already loaded all the 162 countries' information in a DataFrame named `df`, where the column for fertility rates is called `fertility`. How can we filter the countries with fertility rate over 2.88?

*** =instructions
- `df[df['fertility']>2.88]`
- `df[['fertility']>2.88]`
- `high_fert = df['fertility']>2.88
  df[high_fert]`
- Both A and C

*** =hint
You can review Exercise 17, Chapter 3 of "Intermediate Python for Data Science".

*** =pre_exercise_code
```{python}
# pec
import pandas as pd
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_1397/datasets/female_literacy_fertility.csv')
```

*** =sct
```{python}
test_mc(4, msgs = ["This is the best way to filter data, but not the only way.","This doesn't really work.", "This works, but there is also a simpler way to filter data.", "Yes!"])
```

--- type:NormalExercise lang:python xp:100 skills:2 key:830b03fa0a
## Looping over DataFrame
Earlier, we found out that the ten countries with the highest literacy rates are mostly in Europe and have small populations. What about those with high fertility rates? Loop over the DataFrame of all countries with a fertility rates over 2.88 (which you just created), and print the `Continent` and `population` of each one of them.

*** =instructions
- Loop over the labels and rows of the DataFrame `df_high_fert`.
- Print the `Continent` and `population` attributes of each row separately in one `print()` statement.

*** =hint
- Use a for loop over `df_high_fert.iterrows()` to loop over the DataFrame's rows.
- For each `row`, print `row[`Continent`], `row[population]`.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd

df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_1397/datasets/female_literacy_fertility.csv')
df_high_fert = df[df['fertility']>2.88]
```

*** =sample_code
```{python}
# Loop over the labels and rows of df_high_fert
for lab, row in df_high_fert.iterrows():
    print(row['Continent'], row['population'])

```

*** =solution
```{python}
# Loop over the labels and rows of df_high_fert
for lab, row in df_high_fert.iterrows():
    print(row['Continent'], row['population'])
```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:7ab1dcd9db
## Adding a column
To better understand how closely female literacy rates are connected to fertility rates, let's add another column to `df_high_fert` indicating whether the country's female literacy rate is higher than 70 percent.

*** =instructions
- Loop over the labels and rows of `df_high_fert`.
- For each pair of label and row, add a boolean to a new column `high_lit` that indicates whether the country's `female literacy` attribute is larger than 70.
- Print the new DataFrame.

*** =hint
- Use a for loop over `df_high_fert.iterrows()` to loop over the DataFrame's rows.
- Use `df[lab, new_column]` to add a value into a new column of the row with the label `lab`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_1397/datasets/female_literacy_fertility.csv')
df_high_fert = df[df['fertility']>2.88]
```

*** =sample_code
```{python}
# Iterate over the labels and rows of df_high_fert
for lab, row in df_high_fert.iterrows():
    # Add the correct boolean value to the high_lit column
    df.loc[lab, "high_lit"] = row["female literacy"]>70

# Print the result
print(df)

```

*** =solution
```{python}
# solution code
```

*** =sct
```{python}
success_msg("Great work!")
```
