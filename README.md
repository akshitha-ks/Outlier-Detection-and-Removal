# Outlier-Detection-and-Removal

AIM:

   To read the given data and detect outliers and remove it.

EXPLANATION:

   Outliers can be detected using visualization, implementing mathematical formulas on the dataset, or using the statistical approach

ALGORITHM:
       
       Step 1: Read the given data.
       
       Step 2: Detect the outliers from the data.
       
       Step 3: Remove the outliers from the data.
       
       Step 4: Save the required data to the file.

CODE & OUTPUT:

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following.

(1) Remove outliers using IQR

import pandas as pd

df=pd.read_csv("/content/bhp.csv")

q1=df["price_per_sqft"].quantile(0.25)

q3=df["price_per_sqft"].quantile(0.75)

IQR=q3-q1

df_new=df["price_per_sqft"][((df["price_per_sqft"]>=q1-1.5*IQR)&(df["price_per_sqft"]<=q3+1.5*IQR))]

![image](https://github.com/akshitha-ks/Outlier-Detection-and-Removal/assets/123535064/fbaad24a-a0bd-4d3a-b9a4-c74f681cd654)

(2) After removing outliers in step 1, you get a new dataframe.

q1=df["price_per_sqft"].quantile(0.25)

q3=df["price_per_sqft"].quantile(0.75)

df_new=df["price_per_sqft"][((df["price_per_sqft"]>=q1-1.5*IQR)&(df["price_per_sqft"]<=q3+1.5*IQR))]

print(df[ 'price_per_sqft'])

![image](https://github.com/akshitha-ks/Outlier-Detection-and-Removal/assets/123535064/9f528ee5-171d-489a-b98a-8164571b8774)

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

import scipy.stats as stats 

df['price per sqft'] = stats.zscore (df['price_per_sqft'])

print(df['price_per_sqft'])

![image](https://github.com/akshitha-ks/Outlier-Detection-and-Removal/assets/123535064/01033bc4-0bd4-4d54-8101-b8f5612fef2e)

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

import pandas as pd

df=pd.read_csv("/content/height_weight.csv")

q1=df["weight"].quantile(0.25)

q3=df["weight"].quantile(0.75)

IQR-q3-q1

df_new=df["weight"][((df["weight"]>=q1-1.5*IQR)&(df["weight"]<=q3+1.5*IQR))] 

print(df["weight"])

![image](https://github.com/akshitha-ks/Outlier-Detection-and-Removal/assets/123535064/39a11f2c-e3bd-43af-9a42-58312a98ed8e)

(ii) Using IQR, detect height outliers and print them

q1=df[ 'height'].quantile (0.25)

q3=df['height'].quantile (0.75)

IQR=q3-q1

df_new=df['height'][((df[ 'height']>=q1-1.5*IQR)&(df["height"]<=q3+1.5*IQR))]

print(df['height'])

![image](https://github.com/akshitha-ks/Outlier-Detection-and-Removal/assets/123535064/14bee5e9-e84a-4cce-96b9-7b629c9eb156)

RESULT:

      Thus, the given data is read, outliers are detected and removed it and then is saved into file.
