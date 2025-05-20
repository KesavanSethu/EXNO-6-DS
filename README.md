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
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```

![Screenshot 2025-05-13 163010](https://github.com/user-attachments/assets/1d0f7dba-3eca-4cb6-a825-4fb3c5851aa8)

```
df=sns.load_dataset("tips")
df
```

![Screenshot 2025-05-13 163015](https://github.com/user-attachments/assets/d2da2b11-0a0c-42c1-8bc1-1a40f71525fd)

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```

![Screenshot 2025-05-13 163020](https://github.com/user-attachments/assets/8e4a8aaa-e8f7-45d1-8fc5-85e084b50333)

```
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
```

![Screenshot 2025-05-13 163026](https://github.com/user-attachments/assets/2f8836c7-448c-4aa9-b293-7ddd65f95246)

```
tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```

![Screenshot 2025-05-13 163042](https://github.com/user-attachments/assets/c7008e5d-19f0-48dc-b766-b361a12abd2e)

```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
```

![Screenshot 2025-05-13 163049](https://github.com/user-attachments/assets/a5531010-7182-4f35-acc8-b5a134204137)

```
import seaborn as sns
df=sns.load_dataset("tips")
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
```

![Screenshot 2025-05-13 163106](https://github.com/user-attachments/assets/ecc9234a-eecb-4239-ab46-b21a6d8ba4ca)

```
import seaborn as sns
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette="Set1")
plt.xlabel("Totsl Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
```

![Screenshot 2025-05-13 163113](https://github.com/user-attachments/assets/16ca88c9-d5fc-4d47-9520-29bf052b91ed)

```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")
```

![Screenshot 2025-05-13 163118](https://github.com/user-attachments/assets/6a8668b0-2ec5-4edc-8feb-d476d37a668d)

```
import seaborn as sns
import pandas as pd
df=sns.load_dataset('tips')
sns.boxplot(x='day',y='total_bill',hue='sex',data=df,palette='Set2')
```

![Screenshot 2025-05-13 163124](https://github.com/user-attachments/assets/2e4d2b6a-e00f-4ba7-b800-715db60c3619)

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"black"},boxprops={"facecolor":"red","edgecolor":"grey"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":"-","linewidth":2},palette='Set1')
```

![Screenshot 2025-05-13 163129](https://github.com/user-attachments/assets/54b43a9a-aeb4-46e6-9f9b-6c65e864cadd)

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette='Set1',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![Screenshot 2025-05-13 163136](https://github.com/user-attachments/assets/4720cea2-98f6-43df-bfde-b35771014d4a)

```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip,palette="Set2")
```

![Screenshot 2025-05-13 163145](https://github.com/user-attachments/assets/658282b6-931b-4685-a740-3116a4e51b08)

```
import seaborn as sns
sns.set(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"],palette="Set1")
```

![Screenshot 2025-05-13 163154](https://github.com/user-attachments/assets/2cdf21af-8e97-41cb-942e-7aff4f3812de)

```
import seaborn as sns
sns.set(style="whitegrid")
tips = sns.load_dataset("tips")
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")
```

![Screenshot 2025-05-13 163201](https://github.com/user-attachments/assets/ec86aa5e-fdae-4121-b136-d9d3ce107d55)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="layer",linewidth=3,palette='Set2',alpha=0.8)
```

![Screenshot 2025-05-13 163208](https://github.com/user-attachments/assets/0ab520ac-49fa-4c1b-9b65-d204b1cf124b)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set3',alpha=0.8)
```

![Screenshot 2025-05-13 163216](https://github.com/user-attachments/assets/53a55cbe-e716-461e-8bac-ed9250581bf0)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set1',alpha=0.8)
```

![Screenshot 2025-05-13 163222](https://github.com/user-attachments/assets/c4021c2e-bfa6-4a03-b061-b19fd51dde61)

```
import seaborn as sns
tip = sns.load_dataset('tips')
num=tips.select_dtypes(include=['float64','int64']).columns
corr = tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```
![Screenshot 2025-05-13 163228](https://github.com/user-attachments/assets/34a9b8ba-858e-49aa-a42a-8790e74d3d61)

```
sns.heatmap(corr,cmap="YlGnBu")
```
![Screenshot 2025-05-13 163233](https://github.com/user-attachments/assets/a4928299-619b-4208-bfac-d224133b1df2)


# Result:
Thus, Data visualization using seaborn library has been successfully implemented.
