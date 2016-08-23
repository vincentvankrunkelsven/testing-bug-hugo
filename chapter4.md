---
title       : Analyzing World Cup Performance (2)
description : Use dictionary and panda DataFrame to create profiles of artists on spotify.



--- type:NormalExercise lang:python xp:100 skills:2 key:4422544e22
## Panda DataFrame
Recall that we can build a Pandas DataFrame from a dictionary, and store data in a tabular form. Now, let's build a DataFrame using each continent's goal difference profile and a dictionary that store these lists as values.

*** =instructions
- Import pandas as pd
- Create a dictionary `world_cup` with `AF`, `AS`, `CONCACAF`, `EU`, `OC` and `SA` as keys, and the corresponding lists as values.
- Create a DataFrame `world_cup_df` from `world_cup`.
- Print the DataFrame.

*** =hint
- The command to import `x` as `y` is `import x as y`.
- The dictionary should look like this: `{'AF': Africa...}`.
- Use `pd.DataFrame()` to create a DataFrame.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
```

*** =sample_code
```{python}
# Import pandas as pd
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# Print the DataFrame
print(world_cup_df)

```

*** =solution
```{python}
# Import pandas as pd
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# Print the DataFrame
print(world_cup_df)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:a65c7fcf7c
## Changing Labels
Our DataFrame looks great, except that we don't have labels on the rows. Let's add the row labels from the list `continents`.

*** =instructions
- Set the index of `world_cup_df` to `continents`.
- Print the new DataFrame.

*** =hint
- Call the `world_cup_df.index` attribute to set the index.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

```

*** =sample_codes
```{python}
# Import pandas as pd
import pandas as pd

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents

# Print the new DataFrame
print(world_cup_df)

```

*** =solution
```{python}
# Import pandas as pd
import pandas as pd

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents

# Print the new DataFrame
print(world_cup_df)


```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:b617e148c7
## CSV to DataFrame
Creating a DataFrame from a dictionary can be pretty inefficient, and in many cases we create a dataframe just by importing a csv file. In this exercise, you will create the same `world_cup_df` DataFrame by loading `world_cup.csv`

*** =instructions
- Import pandas as pd.
- Read `world_cup.csv` and save it as `world_cup_df`.
- Print the DataFrame.

*** =hint
- The command to import `x` as `y` is `import x as y`.
- Use `pd.read_csv()` to read a csv file into a DataFrame.
- You don't need to change the code for the `print()` statement that we provided.


*** =pre_exercise_code
```{python}
# pec
fn = 'https://s3.amazonaws.com/assets.datacamp.com/production/course_481/datasets/world_cup.csv'
from urllib.request import urlretrieve
urlretrieve(fn, 'world_cup.csv')

```

*** =sample_code
```{python}
# Import pandas as pd
import pandas as pd

# Read world_cup.csv: world_cup_df
world_cup_df = pd.read_csv('world_cup.csv')

# Print the DataFrame
print(world_cup_df)

```

*** =solution
```{python}
# Import pandas as pd
import pandas as pd

# Read world_cup.csv: world_cup_df
world_cup_df = pd.read_csv('world_cup.csv')

# Print the DataFrame
print(world_cup_df)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:MultipleChoiceExercise lang:python xp:100 skills:2 key:537a612b25
## Selecting a column
Recall that in DataFrames, selecting a column by one layer of square brackets returns a different result than selecting it with two layers of square brackets. So what would happen if you print `world_cup_df['AF']`?

*** =instructions
- It will print the DataFrame with `AF` as the only column.
- It will print a Pandas Series including a DataFrame with `AF` as the only column, together with the words "Name: AF, dtype: float64".
- It will print a list of data in the `AF` column.
- It will print a Pandas Series including a list of data in the `AF` column, together with the words "Name: AF, dtype: float64".

*** =hint
- You can enter the command in the IPyhont Shell to see for yourself.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents
```

*** =sct
```{python}
test_mc(correct = 2,
        msgs = ["That would be the result of printing `world_cup_df[['AF']]`.",
                "Yes!", "Using square brackets on DataFrames will not produce a list.", "Using square brackets on DataFrames will not produce a list."])
```

--- type:NormalExercise lang:python xp:100 skills:2 key:3e13e1f5d5

## Using loc and iloc
As we have learned, you can also use `loc` and `iloc` to select columns. The former is label based, while the latter is integer index based. Now, use `loc` to create a Pandas Series with the columns  `CONCACAF` and `SA`, and `iloc` to create a Pandas DataFrame with the column `EU`.

*** =instructions
- Use `loc` on `world_cup_df` to create a Pandas DataFrame with the columns  `CONCACAF` and `SA`. Print the result.
- Use `iloc` on `world_cup_df` to create a Pandas Series with the fourth column. Print the result.

*** =hint
- Use `loc[:,i]` to create the Pandas Series.
- Use `iloc[:,i]` to create the Pandas DataFrame.

*** =pre_exercise_code
```{python}
# pec
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents
```

*** =sample_code
```{python}
# Import pandas as pd
import pandas as pd

# Create a Pandas DataFrame with the columns CONCACAF and SouthAmerica: df
df = world_cup_df.loc[:,["CONCACAF", "SA"]]

# Print df
print(df)

# Create a Pandas Series with the column Europe: ps
ps = world_cup_df.iloc[:,3]

# Print ps
print(ps)

```

*** =solution
```{python}
# Import pandas as pd
import pandas as pd

# Create a Pandas DataFrame with the columns CONCACAF and SouthAmerica: df
df = world_cup_df.loc[:,["CONCACAF", "SA"]]

# Print df
print(df)

# Create a Pandas Series with the column Europe: ps
ps = world_cup_df.iloc[:,3]

# Print ps
print(ps)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:ee84e29795
## Selecting specific entries
Recall that `loc` and  `iloc` allow you to select specific entires by passing both columns and rows as arguments. In this exercise, use `loc` to create a  DataFrame showing `Europe`'s goal difference against `SA`, and use `iloc` to create another one showing the data at column 2, rows 3 and 4.

*** =instructions
- Use `loc` to create a DataFrame showing `SA`'s goal difference against `Europe`.
- Use `iloc` to create a DataFrame showing the data at column 2, rows 3 and 4.

*** =hint
- Pass `[[Europe],[SA]]` to `loc`.
- Pass `[[3,4],[2]]` to `iloc`.

*** =pre_exercise_code
```{python}
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents
```

*** =sample_code
```{python}
# Import pandas as pd
import pandas as pd

# Use `loc` to create a DataFrame showing Europe's goal difference against South America: df1
df1 = world_cup_df.loc[["SA"],["Europe"]]

# Print out df1
print(df1)

# Use `iloc` to create a DataFrame showing the data at column 2, rows 3 and 4: df2
df2 = world_cup_df.iloc[[2,3],[1]]

# Print out df2
print(df2)

```

*** =solution
```{python}
# Import pandas as pd
import pandas as pd

# Use `loc` to create a DataFrame showing Europe's goal difference against South America: df1
df1 = world_cup_df.loc[["SA"],["Europe"]]

# Print out df1
print(df1)

# Use `iloc` to create a DataFrame showing the data at column 2, rows 3 and 4: df2
df2 = world_cup_df.iloc[[2,3],[1]]

# Print out df2
print(df2)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:4c06c44180
## Plotting your array
Let's plot our World Cup data to get an intuitive understanding of the continents' performance against each other. We have created an array `continents` that assign each continent with values 1-6. Subset the first three columns of our 2D array and create a line plot them with `continents` on the x-axis and the goal difference data on the y-axis.

*** =instructions
- Import `matplotlib.pyplot` as `plt`.
- Subset each of the first three columns in `world_cup_df`.
- Plot each of the rows against `continents`.
- Show the plot

*** =hint
- The command to import package `x` as `y` is `import x as y`.
- Use `iloc[:,i]` to subset the ith row of a DataFrame.
- Use `plt.plot()` to create a line plot.
- Use `plt.show()` to show the plot.

*** =pre_exercise_code
```{python}
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents

#Create continents List
continents = [1, 2, 3, 4, 5, 6]
```

*** =sample_code
```{python}
# Imoprt matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset each of the first three columns in world_cup_df: row1, row2, row3
row1 = world_cup_df.iloc[:,0]
row2 = world_cup_df.iloc[:,1]
row3 = world_cup_df.iloc[:,2]

# Plot each of the three columns against continents
plt.plot(continents, row1)
plt.plot(continents, row2)
plt.plot(continents, row3)

# Show the plot
plt.show()

```

*** =solution
```{python}
# Imoprt matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset each of the first three columns in world_cup_df: row1, row2, row3
row1 = world_cup_df.iloc[:,0]
row2 = world_cup_df.iloc[:,1]
row3 = world_cup_df.iloc[:,2]

# Plot each of the three columns against continents
plt.plot(continents, row1)
plt.plot(continents, row2)
plt.plot(continents, row3)

# Show the plot
plt.show()

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:a77d545f6e
## Creating a scatter plot
Create a scatter plot with `continents` on the x-axis and `AS`'s goal difference data on the y-axis.

*** =instructions
- Import `matplotlib.pyplot` as `plt`.
- Subset `AS` from `world_cup_df`.
- Plot both of the rows on a scatter plot.
- Show the plot.

*** =hint
- The command to import package `x` as `y` is `import x as y`.
- Use `.loc[:,i]` to subset the ith row of a DataFrame.
- Use `plt.scatter()` to create a scatter plot.
- Use `plt.show()` to show the plot.


*** =pre_exercise_code
```{python}
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents

#Create continents List
continents = [1, 2, 3, 4, 5, 6]
```

*** =sample_code
```{python}
# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset the goal difference data of Asia in world_cup_df: AS
AS = world_cup_df.loc[:,"AS"]

# Plot both of them on a scatter Plot
plt.scatter(continents, AS)

# Show the plot
plt.show()

```

*** =solution
```{python}
# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset the goal difference data of Asia in world_cup_df: AS
AS = world_cup_df.loc[:,"AS"]

# Plot both of them on a scatter Plot
plt.scatter(continents, AS)

# Show the plot
plt.show()

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:579f6838c2
## Fine-tuning the Plot (1)
Now, it's time to customize the scatter plot you just created. Set the x labels to "continents", and its ticks from `continents` to `continents_codes`. Change the y label to "Asia's goal difference". Finally, set the title of the graph to "Asia's World Cup Goal Difference Against Other Continents". We have already imported `matplotlib.pyplot` as `plt`.

*** =instructions
- Change the x labels to "continents", and its ticks from `continents` to `continents_codes`.
- Change the y label to "Asia's goal difference"
- Set the title of the graph to "Asia's World Cup Goal Difference Against Other Continents".
- Show the customized plot.

*** =hint
- Use `plt.xlabel()` to change x label, and use `xtickcs(old_ticks, new_ticks)` to change x ticks.
- Use `plt.ylabel()` to change y label.
- Use `plt.title()` to set the title of the graph.
- Use `plt.show()` to show the plot

*** =pre_exercise_code
```{python}
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents_names = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents_names

#Create continents List
continents = [1, 2, 3, 4, 5, 6]

# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset the goal difference data of Asia in world_cup_df: AS
AS = world_cup_df.loc[:,"AS"]


continents_codes = ["AF", "AS", "CON","EU","OC", "SA"]

```

*** =sample_code
```{python}
# Create the scatter plot
plt.scatter(continents, AS)

# Set the x labels to continents, and its ticks from continents to continents_names
plt.xlabel('continents')
plt.xticks(continents, continents_codes)

# Set the y label to Asia's goal difference
plt.ylabel("Asia's goal difference")

# Set the title of the graph to Asia's World Cup Goal Difference Against Other Continents
plt.title("Asia's World Cup Goal Difference Against Other Continents")

# Show the customized plot
plt.show()

```

*** =solution
```{python}
# Create the scatter plot
plt.scatter(continents, AS)

# Set the x labels to continents, and its ticks from continents to continents_names
plt.xlabel('continents')
plt.xticks(continents, continents_codes)

# Set the y label to Asia's goal difference
plt.ylabel("Asia's goal difference")

# Set the title of the graph to Asia's World Cup Goal Difference Against Other Continents
plt.title("Asia's World Cup Goal Difference Against Other Continents")

# Show the customized plot
plt.show()

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:91a79380dd
## Fine-tuning the Plot (2)
Now we are going to do some fancier customizations: We will change size of the points to correspond to the six continents' total goal difference ranking, and change their color so that continents in the Eastern Hemisphere are blue, and those in the Western Hemisphere are red. We have already created two lists, `size` and `col` that will help you do that.

*** =instructions
- Set the size of the points to `size`.
- Set the color of the points to `col`.
- Show the plot.

*** =hint
- Pass `s=size` as an argument to `plt.scatter` to set the size of the points.
- Pass `c=col` as an argument to `plt.scatter` to set the colors of the points.
- Use `plt.show()` to show the plot.

*** =pre_exercise_code
```{python}
import pandas as pd

# Lists for continent names and goal difference data
Africa = [0, 0, 0.1, -0.6, 0, -1.1]
Asia = [0, 0, -0.8, -1.5, -0.5, -1.9]
CONCACAF = [-0.1, 0.8, 0, -1.1, -1.5, -1.4]
Europe = [0.6, 1.5, 1.1, 0, 1, -0.1]
Oceania = [0, 0.5, 1.5, -1, 0, -0.3]
SouthAmerica = [1.1, 1.9, 1.4, 0.1, 0.3, 0]

# Create a dictionary of continent profiles: world_cup
world_cup = {'AF': Africa, 'AS': Asia, 'CONCACAF': CONCACAF, 'EU': Europe, 'OC': Oceania, 'SA': SouthAmerica}

# Create a DataFrame from the dictionary: world_cup_df
world_cup_df = pd.DataFrame(world_cup)

# List of continents in the World Cup
continents_names = ['Africa', 'Asia', 'CONCACAF', 'Europe', 'Oceania', 'SouthAmerica']

# Update index of world_cup_df
world_cup_df.index = continents_names

#Create continents List
continents = [1, 2, 3, 4, 5, 6]

# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Subset the goal difference data of Asia in world_cup_df: AS
AS = world_cup_df.loc[:,"AS"]

continents_codes = ["AF", "AS", "CON","EU","OC", "SA"]

size = [160, 80, 120, 240, 200, 280]
col = ["blue","blue","red","blue","blue","red"]
```

*** =sample_code
```{python}
# Create the scatter plot and set the size and color
plt.scatter(continents, AS, s=size, c=col)

# Previous customization
plt.xlabel('continents')
plt.xticks(continents, continents_codes)

plt.ylabel("Asia's goal difference")

plt.title("Asia's World Cup Goal Difference Against Other Continents")

# Show the customized plot
plt.show()

```

*** =solution
```{python}
# Create the scatter plot and set the size and color
plt.scatter(continents, AS, s=size, c=col)

# Previous customization
plt.xlabel('continents')
plt.xticks(continents, continents_codes)

plt.ylabel("Asia's goal difference")

plt.title("Asia's World Cup Goal Difference Against Other Continents")

# Show the customized plot
plt.show()

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:c7465be1be
## Building a histogram
Lastly, we want to create two histograms of Asia's goal difference with bins set to 3 and 6, respectively. Asia's goal difference data is saved as `AS`, and `matplotlib.pyplot` is already imported as `plt`.

*** =instructions
- Create a histogram of `AS` with bins equal to 3. Show the graph.
- Clear the previous graph.
- Create a histogram of `AS` with bins equal to 6. Show the graph.

*** =hint
- Use `plt.hist()` to create a histogram, and pass `bins=3` as an argument.
- Use  `plt.clf()` to clear the graph.
- Use `plt.hist()` to create a histogram, and pass `bins=6` as an argument.

*** =pre_exercise_code
```{python}
AS = [0, 0, -0.8, -1.5, -0.5, -1.9]
import matplotlib.pyplot as plt
```

*** =sample_code
```{python}
# Create a histogram of AS with bins=3
plt.hist(AS, bins=3)

# Show the graph
plt.show()

# Clear the first graph
plt.clf()

# Create a histogram of AS with bins=6
plt.hist(AS, bins=6)

# Show the graph
plt.show()

```

*** =solution
```{python}
# solution code
```

*** =sct
```{python}
success_msg("Great work!")
```
