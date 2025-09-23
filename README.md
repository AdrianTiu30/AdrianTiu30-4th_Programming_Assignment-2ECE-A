# AdrianTiu30-4th_Programming_Assignment-2ECE-A

## ECE BOARD EXAM PROBLEM

### 1. Create DataFrame

### Task
A. Create a filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
B. Create a filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female

### Code Snippet:
```
import pandas as pd

df = pd.read_excel('board2.xlsx')
df

sub = ['Electronics']
Instru = df.loc[(df['Hometown'] == 'Luzon) & (df['Track'] == 'Instrumentation') & (df[sub].mean(axis=1) > 70), ['Name', 'GEAS', 'Electronics']]
Instru.to_csv('Instru.csv')
Instru

subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
Mindy = df.loc[(df['Hometown'] == 'Mindanao') & (df['Gender'] == 'Female') & (df['Average'] >= 55), ['Name', 'Track', 'Electronics', 'Average']]
Mindy.to_csv('Mindy.csv')
Mindy
```

### 1. Create DataFrame

### Task
1. Create a visualization that shows how the different features contributes to average grade.

### Code Snippet:
```
import.matplotlib.pyplot as plt

subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(2,4))
gender_avg = df.groupby('Gender')['Average'].mean()
plt.bar(gender_avg.index, gender_avg.values)
plt.xlabel('Gender')
plt.ylabel('Average Score')

subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(6,4))
hometown_avg = df.groupby('Hometown')['Average'].mean()
plt.bar(hometown_avg.index, hometown_avg.values)
plt.xlabel('Hometown')
plt.ylabel('Average Score')

subs = ['Electronics', 'Math', 'GEAS', 'Communication']
df['Average'] = df[subs].mean(axis=1)
plt.figure(figsize=(6,4))
track_avg = df.groupby('Track')['Average'].mean()
plt.bar(track_avg.index, track_avg.values)
plt.xlabel('Track')
plt.ylabel('Average Score')
```

Interpretation:
- The Gender chart shows the average difference between male and female students
- The Hometown chart shows the average difference between three hometowns, namely: Luzon, Visayas, Mindanao
- The College Track chart shows the average difference between different track fields in college
