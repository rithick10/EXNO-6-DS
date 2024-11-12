# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

## AIM:
  To Perform Data Visualization using seaborn python library for the given datas.

## EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

## CODING AND OUTPUT:

## LINE PLOT:
```PYTHON
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x,y=y)
```

### OUTPUT:
![Screenshot 2024-11-05 111056](https://github.com/user-attachments/assets/094e6472-dab0-4bfa-b592-454521bac1e5)


### SHOW THE DATASET VALUES:
```
df=sns.load_dataset('tips')
df
```

### OUTPUT:

![Screenshot 2024-11-05 111126](https://github.com/user-attachments/assets/36c9e71b-15f2-4b7c-ad57-04f30f821a00)

```PYTHON
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```

### OUTPUT:
![Screenshot 2024-11-05 111133](https://github.com/user-attachments/assets/862cf46b-2665-4d9c-a3cb-8c3129bcc34c)


## MULTI-LINE PLOT:
```PYTHON
x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]

sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)

plt.title("Multi-Line Plot")
plt.xlabel('X label')
plt.ylabel('Y label')
```

### OUTPUT:
![Screenshot 2024-11-05 111142](https://github.com/user-attachments/assets/5784edeb-736a-40fd-a56b-2746e7cbce7d)


## BAR PLOT:
```PYTHON
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset('tips')

avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')

plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
## OUTPUT:
![Screenshot 2024-11-05 111154](https://github.com/user-attachments/assets/8bef24aa-cc2a-4a50-975b-608944e99048)


### CREATE A STACKED BAR PLOT:
```PYTHON
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()

p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)

plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
### OUTPUT:
![Screenshot 2024-11-05 111202](https://github.com/user-attachments/assets/ce7db849-6f63-4ce8-a8c2-9345a86e616a)


```PYTHON
import seaborn as sns
dt=sns.load_dataset('tips')

sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')

plt.xlabel('Day of the week')
plt.ylabel('total Bill')
plt.title('Total Bill by Day and Gender')
```
### OUTPUT:
![Screenshot 2024-11-05 111210](https://github.com/user-attachments/assets/fa52067d-6809-4cd5-a7a7-bfdd76493aa0)

```PYTHON
import seaborn as sns
dr=sns.load_dataset('tips')

sns.histplot(data=dr,x='total_bill',hue='sex',kde=True)

plt.xlabel('Day of the week')
plt.ylabel('total Bill')
plt.title('Total Bill by Day and Gender')
```
### OUTPUT:
![Screenshot 2024-11-05 111218](https://github.com/user-attachments/assets/54477ff9-8f7d-40d2-84ff-9b96f29eae8b)


## USING TIPS DATASET IMPLEMENT SCATTER PLOT OF THE TOTAL BILL VS TIP AMOUNT:
```PYTHON
import seaborn as sns

tips=sns.load_dataset('tips')

sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)

plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
### OUTPUT:
![Screenshot 2024-11-05 111228](https://github.com/user-attachments/assets/47afd048-d678-4b45-948e-8778f3e89d7b)

### VIOLIN PLOT:
```PYTHON
sns.violinplot(x='day',y='total_bill',hue='smoker',data=tips,linewidth=2,width=0.6)

plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Pot of Total Bill by Day and Smoker status")
```

### OUTPUT:

![Screenshot 2024-11-05 111235](https://github.com/user-attachments/assets/b9aabbbe-d384-47f4-b2f8-42afaecb4f90)

```PYTHON
import seaborn as sns

sns.set_theme(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data=tip, palette="hsv")
```

### OUTPUT:

![Screenshot 2024-11-05 111243](https://github.com/user-attachments/assets/6f852b2a-c437-4807-a2d5-43479fe36ecc)

```python
sns.violinplot(x='day', y='tip', hue='sex', data=tip, palette='Set2', split=True, scale='count', inner='quartile', bw=0.5, linewidth=1)
```

### OUTPUT:
![Screenshot 2024-11-05 111250](https://github.com/user-attachments/assets/3c2ecef0-a23d-4c89-b1bd-e7063691f821)


```PYTHON
import seaborn as sns

sns.set_theme(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='tip', y='day', data=tip, palette="Spectral")
```
### OUTPUT:
![Screenshot 2024-11-05 111303](https://github.com/user-attachments/assets/f829ca81-e2e3-43c4-947a-29ae2609f2eb)


```PYTHON
sns.set_theme(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```

### OUTPUT:
![Screenshot 2024-11-05 111315](https://github.com/user-attachments/assets/1a29a4c9-9591-4e98-b092-b3a0f945668c)


### BOX PLOT:
```PYTHON
import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x='day', y='total_bill', hue='sex', data=tips, palette='dark')
```

### OUTPUT:
![Screenshot 2024-11-05 111409](https://github.com/user-attachments/assets/2c4b6f24-0360-4e10-9b0a-cc90d5529cd9)


```python
sns.boxplot(x='day',y='total_bill',hue='smoker',data=tips,linewidth=2,width=0.6,boxprops={"facecolor":"green","edgecolor":"yellow"},whiskerprops={"color":"green","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```

### OUTPUT:

![Screenshot 2024-11-05 111417](https://github.com/user-attachments/assets/824511c9-bae3-48f2-89c0-60e786b0dffb)

### KDE PLOT:
```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='dark',alpha=0.8)
```

### OUTPUT:
![Screenshot 2024-11-05 111426](https://github.com/user-attachments/assets/985c1769-ff4b-455c-8a53-6c654f58a487)


```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='crest',alpha=0.8)
```

### OUTPUT:
![Screenshot 2024-11-05 111437](https://github.com/user-attachments/assets/297f99f5-d250-47c9-99eb-2fbfcec405d8)


```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack', linewidth=3,palette='colorblind',alpha=0.8)
```

### OUTPUT:

![Screenshot 2024-11-05 111447](https://github.com/user-attachments/assets/f759beca-c813-4316-853f-7b48e7e57c6c)

```PYTHON
sns.kdeplot(data=tips, x='total_bill', hue='time', fill=True, alpha=0.4, palette='bright')
sns.rugplot(data=tips, x='total_bill', color='black', height=0.1)
plt.title('KDE Plot with Rug')
plt.show()
```

### OUTPUT:

![Screenshot 2024-11-05 111455](https://github.com/user-attachments/assets/cfe13806-02cd-4bde-bee6-1f293e005c76)

```PYTHON
data=np.random.randint(low=1,high=100,size=(10,10))
print(data)
```
### OUTPUT:
![Screenshot 2024-11-05 111504](https://github.com/user-attachments/assets/139330ac-50e6-4257-90e6-9a4a265979c6)


```PYTHON
hm=sns.heatmap(data=data,annot=True)
```

### OUTPUT:
![Screenshot 2024-11-05 111511](https://github.com/user-attachments/assets/0d3e4043-519a-4297-bbb3-2a993a3de603)


```PYTHON
sns.heatmap(data=data)
```

### OUTPUT:

![Screenshot 2024-11-05 111520](https://github.com/user-attachments/assets/283c114c-d0c6-4663-ad47-ed977b5d2dbf)

```python
custom_palette = sns.color_palette("coolwarm", as_cmap=True)
hm = sns.heatmap(data=data, annot=True, cmap=custom_palette)
plt.title('Heatmap with Custom Coolwarm Palette')
plt.show()
```

### OUTPUT:

![Screenshot 2024-11-05 111530](https://github.com/user-attachments/assets/1f58df13-8376-4792-922a-59d55b167ead)

```PYTHON
hm = sns.heatmap(data=data, annot=True, annot_kws={"size": 10}, cmap='Reds')
plt.title('Heatmap with Custom Annotation Font Size')
plt.show()
```

### OUTPUT:

![Screenshot 2024-11-05 111544](https://github.com/user-attachments/assets/73d18e0b-f480-4e91-8588-b2199d321b98)

```PYTHON
tips=sns.load_dataset("tips")
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()
sns.heatmap(corr,annot=True,cmap="plasma",linewidth=0.5)
```

### OUTPUT:

![Screenshot 2024-11-05 111553](https://github.com/user-attachments/assets/7056c336-90a2-4f7a-9949-8070d658b185)

## RESULT:
Thus the Seaborn Libraries have used and done successfully.
