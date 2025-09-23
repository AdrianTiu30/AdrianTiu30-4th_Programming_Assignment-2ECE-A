# AdrianTiu30-4th_Programming_Assignment-2ECE-A

## ECE BOARD EXAM PROBLEM

### 1. Create DataFrame

### Task
A. Create a filename: Instru = [“Name”, “GEAS”, “Electronics >70”]; where track is constant as Instrumentation and hometown Luzon
B. Create a filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female

### Code:
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

### Output:
```
df
<img width="484" height="752" alt="image" src="https://github.com/user-attachments/assets/a2e87f95-0afe-4219-8d22-03c4576b8dad" />

Instru
<img width="205" height="110" alt="image" src="https://github.com/user-attachments/assets/587218ec-eeb1-4e36-a7dc-c2793556d243" />

Mindy
<img width="326" height="168" alt="image" src="https://github.com/user-attachments/assets/59e27b2e-533a-4caa-94f4-934e269b827b" />
```
