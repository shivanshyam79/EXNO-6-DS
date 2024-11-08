# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

## Name: SHYAM R
## Reg. no: 212223040200

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


import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)

![image](https://github.com/user-attachments/assets/c1a6e1f6-e5e6-4698-a3a5-f872cfd61077)


df=sns.load_dataset("tips")
df

![image](https://github.com/user-attachments/assets/5c1577df-7276-4505-b87a-22184a8fcdde)


sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")


![image](https://github.com/user-attachments/assets/117ddcf2-1e59-4a09-8c90-8477b4d36e4c)


x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")


![image](https://github.com/user-attachments/assets/cc0ebebf-7ecd-4ef9-9360-885302505997)



tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

![image](https://github.com/user-attachments/assets/610bb605-ee82-4c23-ac90-1c425a23541c)


avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

![image](https://github.com/user-attachments/assets/47938bae-6c01-4cd1-b867-e53b0873f93f)


years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)

![image](https://github.com/user-attachments/assets/394954da-7a3f-4f76-9bcb-c2caa293fe74)


import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')

![image](https://github.com/user-attachments/assets/9ed5cfd9-9235-4d76-9fbd-91106a23a564)


import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
tit=pd.read_csv("titanic_dataset.csv")
tit

![image](https://github.com/user-attachments/assets/68160d96-81fc-4c89-97ad-f179c4959a15)


plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")

![image](https://github.com/user-attachments/assets/0b2da205-e146-49d9-b0f9-5965c7c6393a)


plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")

![image](https://github.com/user-attachments/assets/de4c23c6-434e-4834-b1bf-39367dcc8544)


tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')

![image](https://github.com/user-attachments/assets/adef44e5-964d-4b24-b05d-4e9c3d3419b4)


num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var

![image](https://github.com/user-attachments/assets/967d6a76-37d7-4efd-960d-77edbaee01b7)


sns.histplot(data = num_var, kde = True)

![image](https://github.com/user-attachments/assets/a8572f4d-9865-4fda-b20c-7ec88077f9d1)


df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)

![image](https://github.com/user-attachments/assets/d046a336-4477-418f-bdef-0e66f61191fd)


tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])

![image](https://github.com/user-attachments/assets/8806b2dc-10f2-4095-ac74-4d3e91cbfc25)


sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

![image](https://github.com/user-attachments/assets/65b54132-2cda-4685-8cb3-9fbeef7a5d1a)


sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("Age by Passenger Class,Titanic")

![image](https://github.com/user-attachments/assets/1c199a0e-c9f5-4103-84c0-405848d95f90)


sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")

![image](https://github.com/user-attachments/assets/985cc98f-bd4e-4d01-b280-02beb7e17d5e)


import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)

![image](https://github.com/user-attachments/assets/589c46e6-f072-4f7f-a9cb-0dc2da6457c3)


import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])


![image](https://github.com/user-attachments/assets/28956d2c-2961-4efc-8ec0-5edf07aaf09f)


import seaborn as sns
# use to set style of background of plot
sns.set(style="whitegrid")
# loading data-set
tips = sns.load_dataset("tips")
sns.violinplot(x="tip", y="day", data=tip)


![image](https://github.com/user-attachments/assets/0cdadc55-013f-4d68-ae6c-63b2f69cefff)


sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)


![image](https://github.com/user-attachments/assets/07d4afea-6a9e-4dc3-bf67-086525a2db7f)


sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='stack', linewidth=3, palette='Set2', alpha=0.8)


![image](https://github.com/user-attachments/assets/c5ccf937-bdb7-411d-a5ab-45a30582f41b)


import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd  # Import the pandas library
import seaborn as sns
# use pd.read_csv to call the function from the pandas library
mart = pd.read_csv("/content/supermarket.csv")
mart

![image](https://github.com/user-attachments/assets/92cec563-3507-4ff2-9459-904838e9f58f)


mart=mart[['Gender','Payment','Unit price','Quantity','Total','gross income']]
mart.head(10)


![image](https://github.com/user-attachments/assets/3f6292d8-6c89-4629-ad7c-846559d788c0)


sns.kdeplot(data=mart,x='Total')


![image](https://github.com/user-attachments/assets/62088c50-12b5-4290-a69b-d531f181bc65)


sns.kdeplot(data=mart,x='Unit price')


![image](https://github.com/user-attachments/assets/ca455ca4-84de-45c2-95d2-0f6c91262c99)


sns.kdeplot(data=mart)


![image](https://github.com/user-attachments/assets/65f3d8dc-abbb-419a-a616-3200efcfc8ce)


sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack')


![image](https://github.com/user-attachments/assets/e576af7d-f251-450f-8935-8b60939d1c0a)


sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack',linewidth=5,palette='Dark2',alpha=0.5)


![image](https://github.com/user-attachments/assets/fbf77050-0efb-4ed7-bcae-f2153eba0263)


sns.kdeplot(data=mart,x='Unit price',y='gross income')


![image](https://github.com/user-attachments/assets/93b7bdf6-3b7f-4f2d-bcea-8ceb6c0ae7fe)


data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted")
print(data)


The data to be plotted
[[69 71 21  7 98 13  8 49 56  4]
 [98  9 72 89 31 24 31 13 42 75]
 [87 52  8 74 78 53 32 48  7 29]
 [56 70 63 52 66 51 45 87 93 21]
 [71 92 69 26 14 22 23 98 24 60]
 [66 93 22 32 13 21 99 23 37 43]
 [ 2 46 56 85  9 97 47 87 84 44]
 [94 24 27 35 93 16 56 77 20 30]
 [70 97 31 80 66 60 46 72 38 55]
 [47 88 94 62  5 34 26 24  4 43]]


 hms=sns.heatmap(data=data)


![image](https://github.com/user-attachments/assets/7279a857-efc3-4a62-9cdc-8777a0546048)


hms=sns.heatmap(data=data,annot=True)


![image](https://github.com/user-attachments/assets/b7968d75-b4e9-40df-8108-7d51242a007d)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
