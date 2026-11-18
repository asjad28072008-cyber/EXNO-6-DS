# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

 ```
import seaborn as sns
import matplotlib.pyplot as plt
x= [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x, y=y)
```

<img width="666" height="505" alt="image" src="https://github.com/user-attachments/assets/3ad5bc3e-6eae-4487-870b-c168ba7aa71b" />



```
df=sns.load_dataset("tips")
df
```

<img width="588" height="462" alt="image" src="https://github.com/user-attachments/assets/87b5ad43-41c0-4b15-9ae0-8695826df375" />


```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```

<img width="720" height="540" alt="image" src="https://github.com/user-attachments/assets/95462876-770d-4714-88c5-3b6d9b1940ee" />


```
x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
#Set plot title and axis labels
plt.title("Multi-Line Plot")
plt.xlabel("X Label")
plt.ylabel("Y Label")
```


<img width="732" height="560" alt="image" src="https://github.com/user-attachments/assets/26350af7-6839-471f-b0f6-bc7d6cfbee62" />



```
import seaborn as sns
import matplotlib.pyplot as plt
# Load the tips dataset
tips=sns.load_dataset('tips')
#Calculate the average total bill and tip for each day of the week
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()

```

<img width="1710" height="85" alt="image" src="https://github.com/user-attachments/assets/8acca4e0-ecb4-4ab1-ad28-8ffde3b6da53" />




```
plt.figure(figsize=(8, 6))
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2= plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
#Set the labels and title
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```

<img width="826" height="617" alt="image" src="https://github.com/user-attachments/assets/cff609e3-a9e0-47ae-8de0-03b00de38790" />


```
avg_total_bill = tips.groupby('time') ['total_bill'].mean()
avg_tip = tips.groupby('time') ['tip'].mean()
# Create a grouped bar chart
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```

<img width="1017" height="592" alt="image" src="https://github.com/user-attachments/assets/862fe7fc-6daa-4dbe-b5f8-3827d29f909f" />


```
years = range(2000, 2012)
apples =[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges =[0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

<img width="707" height="491" alt="image" src="https://github.com/user-attachments/assets/a1390fe9-9fb5-491d-b9ab-3448bf3aa85d" />


```
import seaborn as sns
dt =sns.load_dataset('tips')
# Bar plot with hue parameter
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
# Set labels and title
#Set labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```

<img width="712" height="527" alt="image" src="https://github.com/user-attachments/assets/1ffa7c79-1364-40f2-9cf0-eb621c6d884c" />


```

import pandas as pd
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```

<img width="1276" height="433" alt="image" src="https://github.com/user-attachments/assets/90ea8fad-edd9-4c9d-b0c5-95de58656d3a" />


```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

<img width="1125" height="610" alt="image" src="https://github.com/user-attachments/assets/233fdf91-7465-45ec-b24a-72c6d402f3c3" />


```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

<img width="846" height="535" alt="image" src="https://github.com/user-attachments/assets/727beb80-56e1-4c2a-bc93-feda34ad40bf" />


```
import seaborn as sns
# Load the tips dataset
tips =sns.load_dataset('tips')
# Scatter plot of total bill vs. tip amount
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
# Set labels and title
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

<img width="786" height="520" alt="image" src="https://github.com/user-attachments/assets/930e8113-4d23-4685-9391-320353c38d2b" />



```
#Generating dataset of random numbers
import numpy as np
np.random.seed(1)
num_var =np.random.randn(1000)
num_var =pd.Series(num_var, name = "Numerical variable")
num_var
```

<img width="360" height="487" alt="image" src="https://github.com/user-attachments/assets/85088918-200f-4c1f-98f5-a4c4a15d1aba" />


```
sns.histplot(data=num_var,kde=True)
```

<img width="755" height="505" alt="image" src="https://github.com/user-attachments/assets/28b88063-d5bb-4ec3-aa72-abe141621ccc" />


```
df=pd.read_csv('/content/titanic_dataset.csv')
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

<img width="740" height="492" alt="image" src="https://github.com/user-attachments/assets/17a29cb7-cc3f-45e0-b280-a24751367040" />


```
np.random.seed(0)
marks = np.random.normal ( loc = 70, scale=10, size=100)
marks
```

<img width="682" height="396" alt="image" src="https://github.com/user-attachments/assets/acfb27e4-dd27-4957-8cc3-5a284dde83a2" />


```
sns.histplot(data=marks, bins =10, kde =True, stat='count', cumulative=False, multiple='stack', element='bars', palette='Set1', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')
```

<img width="726" height="537" alt="image" src="https://github.com/user-attachments/assets/ab6daef5-c0b4-4eb6-8d13-330954e36c7f" />


```
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```

<img width="717" height="480" alt="image" src="https://github.com/user-attachments/assets/a9b20605-0bde-48ce-80c9-fcd81fa3aa1f" />


```
sns.boxplot(x="day", y="total_bill", hue="smoker", data= tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```


<img width="670" height="502" alt="image" src="https://github.com/user-attachments/assets/d169f07f-68ec-4045-ba42-a6b346dbf9fa" />


```
sns.boxplot(x='Pclass',y='Age', data=df, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")
```

<img width="1117" height="602" alt="image" src="https://github.com/user-attachments/assets/a36cae63-2ff5-4bad-9498-b10917d4c7e1" />


```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
palette="Set3", inner="quartile")
#Add labels and title
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

<img width="675" height="540" alt="image" src="https://github.com/user-attachments/assets/a6e934a7-6d09-412d-b32f-219f376eb79b" />


```
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')

sns.violinplot(x = 'day', y ='tip', data = tip)
```

<img width="692" height="500" alt="image" src="https://github.com/user-attachments/assets/15f32650-df03-4e9a-a0aa-839256333b1c" />


```
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])

```

<img width="667" height="500" alt="image" src="https://github.com/user-attachments/assets/acd37ea7-d503-480c-a5fe-3bedc06a5670" />


```


# use to set style of background of plot
sns.set(style="whitegrid")
# loading data-set
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip)


```

<img width="748" height="520" alt="image" src="https://github.com/user-attachments/assets/b7781525-1b81-4011-b52d-4991267d2842" />


```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```


<img width="807" height="502" alt="image" src="https://github.com/user-attachments/assets/e2941f1d-7d77-44e4-adba-23b2a4c6de1f" />


```
sns.kdeplot( data=tips, x='total_bill', hue='time', multiple='layer', linewidth=3, palette='Set2',alpha=0.8)
```

<img width="745" height="502" alt="image" src="https://github.com/user-attachments/assets/29e83dab-1c2b-444e-aad1-253028a0c6d9" />


```
sns.kdeplot(data=tips,x= 'total_bill', hue='time', multiple='stack', linewidth=3, palette='Set2',alpha=0.8)

```

<img width="760" height="515" alt="image" src="https://github.com/user-attachments/assets/6c3412e7-5a99-459a-92f7-6322c95c5f90" />



```
df=pd.read_csv('/content/titanic_dataset.csv')
df
```

<img width="1295" height="447" alt="image" src="https://github.com/user-attachments/assets/d29d5328-fedd-408d-a74e-8c2bd26e2b8f" />


```
sns.kdeplot(data=df,x='Age')
```

<img width="752" height="495" alt="image" src="https://github.com/user-attachments/assets/12eb84ab-9dff-437f-b839-d80f53d27b28" />


```
sns.kdeplot(data=df,x='Age',y='Pclass')
```

<img width="747" height="507" alt="image" src="https://github.com/user-attachments/assets/6908828b-3b8a-417c-b770-2730ce497da7" />


```
sns.kdeplot(data=df,x='Age',y='Pclass',hue='Survived',multiple='layer')
```

<img width="755" height="512" alt="image" src="https://github.com/user-attachments/assets/9799c206-266a-438b-aa75-d3b3916a5ec4" />


```
data= np.random.randint(low = 1, high = 100, size = (10,10))
print("The data to be plotted: \n")
print(data)
```

<img width="380" height="241" alt="image" src="https://github.com/user-attachments/assets/4b4e95b9-4749-4ebd-92c2-ca33269c7129" />


```
hm=sns.heatmap(data=data)
hm
```


<img width="722" height="477" alt="image" src="https://github.com/user-attachments/assets/5935bae8-b411-4b70-a213-5c545f0fb3e7" />


# Result:

Thus, all the data visualization techniques of seaborn has been implemented.
