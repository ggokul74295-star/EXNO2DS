# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT

import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df

<img width="1027" height="362" alt="Screenshot 2025-10-17 113710" src="https://github.com/user-attachments/assets/eaeae71e-cb13-4256-bf17-d54ae6d7963a" />

df.info()

<img width="499" height="455" alt="Screenshot 2025-10-17 113729" src="https://github.com/user-attachments/assets/d8a4ab44-8896-4cc2-a1bf-566aa3e94da4" />

df.head()

<img width="1018" height="178" alt="Screenshot 2025-10-17 113746" src="https://github.com/user-attachments/assets/30090d8f-f497-4002-b65d-a19a7b5ee3eb" />

df.nunique()

<img width="233" height="327" alt="Screenshot 2025-10-17 113757" src="https://github.com/user-attachments/assets/e0d83cee-5d82-4a0e-b3aa-960c57f2a661" />

df["Survived"].value_counts()

<img width="327" height="97" alt="Screenshot 2025-10-17 113812" src="https://github.com/user-attachments/assets/a13031a6-b3a8-451b-9648-b786ca5c0b55" />

sns.countplot(data=df,x="Survived")

<img width="874" height="660" alt="Screenshot 2025-10-17 113850" src="https://github.com/user-attachments/assets/815b1039-f949-4d11-880b-bbbf58c72882" />

df.rename(columns={"Sex" : 'Gender'}, inplace=True)
df

<img width="1005" height="362" alt="Screenshot 2025-10-17 113902" src="https://github.com/user-attachments/assets/7e485ceb-72dc-4d5a-86db-42e7f86c39c9" />

sns.catplot(x="Gender",col="Survived",kind="count", data=df,height=5,aspect=.7)

<img width="1002" height="695" alt="Screenshot 2025-10-17 113916" src="https://github.com/user-attachments/assets/ec784f95-ab8a-4c56-b46d-024d79b5f9d8" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="858" height="736" alt="Screenshot 2025-10-17 113938" src="https://github.com/user-attachments/assets/e5195b51-a8c8-4726-bbec-6d2a5aadbdc1" />

df.boxplot(column="Age",by="Survived")

<img width="795" height="689" alt="Screenshot 2025-10-17 113950" src="https://github.com/user-attachments/assets/73b3561d-5ad2-458a-9946-3d229a222761" />

sns.scatterplot(x=df["Age"],y=df['Fare'])

<img width="828" height="651" alt="Screenshot 2025-10-17 114002" src="https://github.com/user-attachments/assets/a0717ca7-9b87-42f0-9ec1-4de2763265fd" />

sns.jointplot(x="Age",y="Fare",data=df)

<img width="959" height="873" alt="Screenshot 2025-10-17 114016" src="https://github.com/user-attachments/assets/436f8c87-bc62-4d89-9126-050b495e9907" />

fig,ax1=plt.subplots (figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass', y='Age', hue='Gender', data=df)

<img width="995" height="602" alt="Screenshot 2025-10-17 114031" src="https://github.com/user-attachments/assets/393c7b24-5695-4c1b-93e1-3608ef2cfa14" />

corr = df. select_dtypes (include=['number']). corr()
sns. heatmap(corr,annot=True)

<img width="887" height="724" alt="Screenshot 2025-10-17 114051" src="https://github.com/user-attachments/assets/0befe873-1249-47fd-95b8-d294d1291b0d" />

sns.catplot(data=df, col="Survived", x="Gender", hue="Pclass",kind="count")

<img width="1032" height="506" alt="Screenshot 2025-10-17 114108" src="https://github.com/user-attachments/assets/14be7048-3e5f-482c-be6f-72220bd20576" />

# RESULT
       To perform Exploratory Data Analysis on the given data set is succesfully completed.
