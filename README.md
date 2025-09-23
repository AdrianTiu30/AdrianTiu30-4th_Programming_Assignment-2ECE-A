# AdrianTiu30-4th_Programming_Assignment-2ECE-A

## ECE BOARD EXAM PROBLEM

### This is a python script code that uses Data Wrangling and Visualization Techniques based on specified conditions

### Task:
A. Create a filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as 
Instrumentation and hometown Luzon

B. Create a filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown 
is constant as Mindanao and gender Female

### Code Snippet:
```
import pandas as pd

# Read file and print
df = pd.read_excel('board2.xlsx')
df
```
Import pandas library. Use the function .read() in order to read the specified file and print its contents
```
# Display specified value with constants (hometown == Luzon, track == Instrumentation) saved under filename Instru
sub = ['Electronics']
Instru = df.loc[(df['Hometown'] == 'Luzon) & (df['Track'] == 'Instrumentation') & (df[sub].mean(axis=1) > 70), ['Name', 'GEAS', 'Electronics']]
Instru.to_csv('Instru.csv')
Instru
```
Create an array that stores the values inside the element "ELECTRONICS". Using the filename instru, access the data inside the file using .loc() with parameters set to "Hometown" as "Luzon", "Track" as "Instrumentation", and scores in the "Electronics" subject that is greater than 70. Using .mean(axis=1) to get the average scores in the "Electronics" column. Display the values of the columns "Name", "GEAS", and "Electronics" that satisfies the given conditions in the previous line of code. ["Name", "GEAS", "Electronics"]
```
# Display specified value with constants (hometown == Mindanao, Gender == Female, Average >= 55) saved under filename Mindy
subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
Mindy = df.loc[(df['Hometown'] == 'Mindanao') & (df['Gender'] == 'Female') & (df['Average'] >= 55), ['Name', 'Track', 'Electronics', 'Average']]
Mindy.to_csv('Mindy.csv')
Mindy
```
Create an array that stores the values of the four (4) subjects, namely: "Electronics", "Math", "GEAS", "Communication". Using the filename Mindy, access the data inside the file using .loc() with parameters set to "Hometown" as "Mindanao", "Gender" as "Female", and the general average scores of the students in all subjects that is greater than or equal to 55. Using .mean(axis=1) to get the average scores in all the subjects by column. Display the values of the columns "Name", "Track", "Electronics" and the value for the the general average of the students that satisfies the given conditions in the previous line of code. The output should have ["Name", "track", "Electronics", "Average"]

### 2. Visualization

### Task:
#### Create a visualization that shows how the different features contributes to average grade.

### Code Snippet:
```
import.matplotlib.pyplot as plt
```
Import matplotlib library to access built-in-functions that will help create various types of plots and visualization.
```
# Bar graph visualization for Gender Average
subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(2,4))
gender_avg = df.groupby('Gender')['Average'].mean()
plt.bar(gender_avg.index, gender_avg.values)
plt.xlabel('Gender')
plt.ylabel('Average Score')
```
Create an array that stores the values of "Electronics", "Math", "GEAS", and "Communication". Get the mean of the subjects using .mean(axis=1) then assign the value in the dataframe named "Average". Set the figure size to a specified dimension that is appropriate for the data set. Create a new variable that stores the grouped by value of the column "Gender" and the value of the "Average" dataframe. Set the x and y axis of the bar using .bar() and label each axis using .xlabel() and .ylabel(). The output should show the average grade of all the students in all the subjects but is grouped by gender, regardless of their hometown and track.
```
# Bar graph visualization for hometown Average
subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(6,4))
hometown_avg = df.groupby('Hometown')['Average'].mean()
plt.bar(hometown_avg.index, hometown_avg.values)
plt.xlabel('Hometown')
plt.ylabel('Average Score')
```
Create an array that stores the values of "Electronics", "Math", "GEAS", and "Communication". Get the mean of the subjects using .mean(axis=1) then assign the value in the dataframe named "Average". Set the figure size to a specified dimension that is appropriate for the data set. Create a new variable that stores the grouped by value of the column "Hometown" and the value of the "Average" dataframe. Set the x and y axis of the bar using .bar() and label each axis using .xlabel() and .ylabel(). The output should show the average grade of all the students in all the subjects but is grouped by hometown, regardless of their gender and track.
```
# Bar graph visualization for Track Average
subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(6,4))
track_avg = df.groupby('Track')['Average'].mean()
plt.bar(track_avg.index, track_avg.values)
plt.xlabel('Track')
plt.ylabel('Average Score')
```
Create an array that stores the values of "Electronics", "Math", "GEAS", and "Communication". Get the mean of the subjects using .mean(axis=1) then assign the value in the dataframe named "Average". Set the figure size to a specified dimension that is appropriate for the data set. Create a new variable that stores the grouped by value of the column "Track" and the value of the "Average" dataframe. Set the x and y axis of the bar using .bar() and label each axis using .xlabel() and .ylabel(). The output should show the average grade of all the students in all the subjects but is grouped by track, regardless of their gender and hometown.

Interpretation:
- The Gender chart shows the average difference between male and female students
- The Hometown chart shows the average difference between three hometowns, namely: Luzon, Visayas, Mindanao
- The College Track chart shows the average difference between different track fields in college

# --Version 2--
