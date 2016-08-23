---
title       : How popular is Snapchat?
description : In this chapter you will practice string methods, list methods, using functions from imported packages and numpy arrays. We will use the search interest data of Snapchat on Google as a case study.

attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:NormalExercise lang:python xp:100 skills:2 key:2e61fdc75e
## Search interest for Snapchat
Google's search interest reflects how many searches there are for a specific term over a week, where 100 represents the highest historical search number for this term, and 0 means no search at all. We have loaded a list named `snapchat_2016` that has snapchat's search interest from the first week of 2016 up to the week ending on August 20.

We know that at more than one occasions the search interest was exactly 50. Use the list object's built-in methods to find the index of the first time this happened and the total number of such occurence.

*** =instructions
- Find the index of 50 in the list `snapchat_2016`.
- Find the count of 50 in the list `snapchat_2016`.

*** =hint
- Use the method `index` to find the index of an element in a list.
- Use the method `count` to find how many times an element appears in a list.

*** =pre_exercise_code
```{python}
# pec
snapchat_2016 = [47, 43, 45, 46, 47, 49, 50, 51, 54, 55, 55, 58, 71, 57, 57, 60, 61, 58, 55, 56, 61, 62, 59, 58, 60, 60, 64, 62, 67, 62, 72, 54, 50]

```

*** =sample_code
```{python}
# Find the index of 50 in snapchat_2016: ind
ind = snapchat_2016.index(50)

# Find the count of 50 in snapchat_2016: count
count = snapchat_2016.count(50)

# Print the results
print(ind, count)

```

*** =solution
```{python}
# Find the index of 50 in snapchat_2016: ind
ind = snapchat_2016.index(50)

# Find the count of 50 in snapchat_2016: count
count = snapchat_2016.count(50)

# Print the results
print(ind, count)

```

*** =sct
```{python}
success_msg("Great!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:a418d3f26c
## Removing Wrong Records

It just so happened that all records with a search interest of 50 are wrong, and we have to remove them from our list. We have learned a method to remove the first appearance of an element from a list, and from last exercise we know that 50 appears twice in the list, so we can achieve our task by using that method twice. However, now that even Google makes mistakes, we just can't trust anything anymore. Therefore, we will check the length of `snapchat_2016` before and after the removal to see if it has indeed decreased by 2.

*** =instructions
- Find the length of `snapchat_2016`.
- Remove 50 from `snapchat_2016` twice.
- Find the new length of `snapchat_2016`.
- Print the difference between the old length and the new one.

*** =hint
- Use the function `len` to find the length of `snapchat_2016`.
- Use the method `remove()` to remove an element from a list.
- Use the function `len` to find the new length of `snapchat_2016`.
- You don't need to change the code for the `print()` statement that we provided.

*** =pre_exercise_code
```{python}
# pec
snapchat_2016 = [47, 43, 45, 46, 47, 49, 50, 51, 54, 55, 55, 58, 71, 57, 57, 60, 61, 58, 55, 56, 61, 62, 59, 58, 60, 60, 64, 62, 67, 62, 72, 54, 50]

```

*** =sample_code
```{python}
# Find the length of snapchat_2016: length
length = len(snapchat_2016)

# Remove 50 from snapchat_2016 for three times
snapchat_2016.remove(50)
snapchat_2016.remove(50)

# Find the new length of snapchat_2016: new_length
new_length = len(snapchat_2016)

# Print the difference between the old length and the new one
print(length-new_length)

```

*** =solution
```{python}
# Find the length of snapchat_2016: length
length = len(snapchat_2016)

# Remove 50 from snapchat_2016 for three times
snapchat_2016.remove(50)
snapchat_2016.remove(50)

# Find the new length of snapchat_2016: new_length
new_length = len(snapchat_2016)

# Print the difference between the old length and the new one
print(length-new_length)


```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:94e68dfed4
## Reversing the list
The executives of Snapchat want to examine their app's search interest backwards, starting from the most recent record all the way down to the beginning of the year. Use a list method to achieve that.

We also want to append the last week of 2015 into the now reversed search interest data, because part of that week was in 2016. The search interest of that week is stored as `snapchat_2015_last`.

*** =instructions
- Reverse `snapchat_2016` and save it as `snapchat_2016_rev`.
- Append `snapchat_2015_last` to `snapchat_2016_rev`.
- Print the reversed list.

*** =hint
- Reverse `snapchat_2016` and save it as `snapchat_2016_rev`.
- Append `snapchat_2015_last` to `snapchat_2016_rev`.
- Print the reversed list.

*** =pre_exercise_code
```{python}
# pec
snapchat_2016 = [47, 43, 45, 46, 47, 49, 51, 54, 55, 55, 58, 71, 57, 57, 60, 61, 58, 55, 56, 61, 62, 59, 58, 60, 60, 64, 62, 67, 62, 72, 54]

snapchat_2015_last = 52

```

*** =sample_code
```{python}
# Reverse snapchat_2016: snapchat_2016_rev
snapchat_2016.reverse()

# Append snapchat_2015_last to snapchat_2016_rev
snapchat_2016.append(snapchat_2015_last)

# Print the resulting list
print(snapchat_2016)

```

*** =solution
```{python}
# Reverse snapchat_2016: snapchat_2016_rev
snapchat_2016.reverse()

# Append snapchat_2015_last to snapchat_2016_rev
snapchat_2016.append(snapchat_2015_last)

# Print the resulting list
print(snapchat_2016)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:aa6643f19f
## From list to numpy array
Now we are going to shift gear and start working with numpy arrays instead of lists. But first of all, we need to tranform `snapchat_2016` from a list to an array object. Import `numpy` as `np` and create an array named `snapchat_2016np` from `snapchat_2016`.

*** =instructions
- Import `numpy` as `np`.
- Create a numpy array named `snapchat_2016np` from `snapchat_2016`.

*** =hint
- The command to import a package `x` is `import x`.
- Use `np.array()` to create a numpy array.

*** =pre_exercise_code
```{python}
# pec
snapchat_2016 =  [54, 72, 62, 67, 62, 64, 60, 60, 58, 59, 62, 61, 56, 55, 58, 61, 60, 57, 57, 71, 58, 55, 55, 54, 51, 49, 47, 46, 45, 43, 47, 52]

```

*** =sample_code
```{python}
# Import numpy as np
import numpy  as np

# Transform pascal_13 to a numpy array: pascal_13np
snapchat_2016np = np.array(snapchat_2016)

# Print the resulting array
print(snapchat_2016np)

```

*** =solution
```{python}
# Import numpy as np
import numpy  as np

# Transform pascal_13 to a numpy array: pascal_13np
snapchat_2016np = np.array(snapchat_2016)

# Print the resulting array
print(snapchat_2016np)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:b283a45bf0
## Import only numpy.array

Recall that we can also just import a particular function in a package. In this exercise, repeat what you just did, but importing only `array` from `numpy`.

*** =instructions
- Import `array` from `numpy`.
- Create a numpy array named `snapchat_2016np` from `snapchat_2016`.

*** =hint
- The command to import `y` from package `x` is `from x import y`.
- Use `array()` to create a numpy array.

*** =pre_exercise_code
```{python}
# pec
snapchat_2016 =  [54, 72, 62, 67, 62, 64, 60, 60, 58, 59, 62, 61, 56, 55, 58, 61, 60, 57, 57, 71, 58, 55, 55, 54, 51, 49, 47, 46, 45, 43, 47, 52]

```

*** =sample_code
```{python}
# Import numpy as np
import numpy  as np

# Transform pascal_13 to a numpy array: pascal_13np
snapchat_2016np = np.array(snapchat_2016)

# Print the resulting array
print(snapchat_2016np)

```

*** =solution
```{python}
# Import numpy as np
import numpy  as np

# Transform pascal_13 to a numpy array: pascal_13np
snapchat_2016np = np.array(snapchat_2016)

# Print the resulting array
print(snapchat_2016np)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:eb349a739b
## Subsetting Array
Recall that you can subset numpy arrays just like lists. In this exercise, print snapchat's search interest in the 10th most recent week and a subset of its search interest for the last four weeks. Remember the array is still organized in reverse time order.

*** =instructions
- Subset the 10th element of `snapchat_2016np`.
- Subset the first 4 elements of `snapchat_2016np`.

*** =hint
- Use `array[i]` to select the ith element of an array.
- Use `array[:i]` to select a subset of an array ending at the ith element.

*** =pre_exercise_code
```{python}
import numpy as np
snapchat_2016np =  np.array([54, 72, 62, 67, 62, 64, 60, 60, 58, 59, 62, 61, 56, 55, 58, 61, 60, 57, 57, 71, 58, 55, 55, 54, 51, 49, 47, 46, 45, 43, 47, 52])

```

*** =sample_code
```{python}
# Select the 10th element of snapchat_2016np: week_10
week_10 = snapchat_2016np[9]

# Subset the first four weeks in snapchat_2016np: four_weeks
four_weeks = snapchat_2016np[:4]

# Print both subsets
print(week_10, four_weeks)

```

*** =solution
```{python}
# Select the 10th element of snapchat_2016np: week_10
week_10 = snapchat_2016np[9]

# Subset the first four weeks in snapchat_2016np: four_weeks
four_weeks = snapchat_2016np[:4]

# Print both subsets
print(week_10, four_weeks)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:4000e555cd
## Mean and Median
In the last exercise, we noticed that Snapchat's search interest for the last four weeks tend to be significantly higher than the 10th most recent week, a week that we chose randomly. Is it possible that for the last four weeks, Snapchat has garnered more interest than its average search interest in 2016? Let's test that with mean and median.

*** =instructions
- Import `numpy` as `np`
- Calculate the mean of `four_weeks` and `snapchat_2016np`.
- Calculate the median of `four_weeks` and `snapchat_2016np`.

*** =hint
- To import `x` as `y`, use the command `import x as y`.
- Use `np.mean()` to calculate mean.
- Use `np.median` to calculate median.

*** =pre_exercise_code
```{python}
import numpy as np
snapchat_2016np =  np.array([54, 72, 62, 67, 62, 64, 60, 60, 58, 59, 62, 61, 56, 55, 58, 61, 60, 57, 57, 71, 58, 55, 55, 54, 51, 49, 47, 46, 45, 43, 47, 52])
four_weeks = snapchat_2016np[:3]
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Calculate the mean of four_weeks and snapchat_2016np: mean_four_weeks, mean_2016
mean_four_weeks = np.mean(four_weeks)
mean_2016 = np.mean(snapchat_2016np)

# Calculate the median of four_weeks and snapchat_2016np: med_four_weeks, med_2016
med_four_weeks = np.median(four_weeks)
med_2016 = np.median(snapchat_2016np)

# Print the means and the medians
print(mean_four_weeks, mean_2016, med_four_weeks, med_2016)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Calculate the mean of four_weeks and snapchat_2016np: mean_four_weeks, mean_2016
mean_four_weeks = np.mean(four_weeks)
mean_2016 = np.mean(snapchat_2016np)

# Calculate the median of four_weeks and snapchat_2016np: med_four_weeks, med_2016
med_four_weeks = np.median(four_weeks)
med_2016 = np.median(snapchat_2016np)

# Print the means and the medians
print(mean_four_weeks, mean_2016, med_four_weeks, med_2016)

```

*** =sct
```{python}
success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:2 key:af0822f65e
## Standard Deviation
It seems that Snapchat has indeed attracted more attention in the last four weeks! However, we know that things like search interest can fluctuate randomly, so we want to know how likely this change is just due to chance. Standard deviation is a great tool to tell how much flucuation there is in our dataset. Now, find the standard deviation of `snapchat_2016np` now.

*** =instructions
- Import `numpy` as `np`.
- Calculate the standard deviation of `snapchat_2016np` and save it to `snapchat_std`.

*** =hint
- To import a package `x` with alias `y`, use the command `import x as y`.
- Use `np.std()` to calculate the standard deviation of a list.

*** =pre_exercise_code
```{python}
# pec
import numpy as np
snapchat_2016np = np.array([54, 72, 62, 67, 62, 64, 60, 60, 58, 59, 62, 61, 56, 55, 58, 61, 60, 57, 57, 71, 58, 55, 55, 54, 51, 49, 47, 46, 45, 43, 47, 52])
```

*** =sample_code
```{python}
# Import numpy as np
import numpy as np

# Calculate the standard deviation of snapchat_2016np: snapchat_std
snapchat_std = np.std(snapchat_2016np)

# Print the standard deviation
print(snapchat_std)

```

*** =solution
```{python}
# Import numpy as np
import numpy as np

# Calculate the standard deviation of snapchat_2016np: snapchat_std
snapchat_std = np.std(snapchat_2016np)

# Print the standard deviation
print(snapchat_std)

```

*** =sct
```{python}
success_msg("Great work!")
```
