# Data-Analysis-Project-in-Python-Cars-Data-
## CARS DATASET
Here, the data of different cars are given with thier specifications.</br >
This data is available as a CSV file. We are going to analyze this dataset using pandas data frame.

The commands that I used in this project :

* import pandas as pd -- To import Pandas library
* pd.read_csv - To import the CSV file in Jupyter notebook
* head() - It shows the first N rows in the data (by default, N=5)
* shape - It shows the total no. of rows and no. of columns of the dataframe
* df.isnull( ).sum( ) - It detects the missing values from each column of the dataframe.
* fillna() - To fill the null values of a column with some particular value
* value_counts - In a column, it shows all the unique values with their count. It can be applied to a single column only.
* isin() - To show all records including particular elements
* apply() - To apply a function along any axis of DF

``` py
import pandas as pd
import warnings
warnings.filterwarnings("ignore")

df=pd.read_csv("cars_data1.csv")

df.head(5)

df.shape

Q. 1) Instruction ( For Data Cleaning ) Find all Null Values in the dataset. If there is any null value in any column, then fill it with the mean of int data type and "N/A" to string datatype of that column.

for column in df:    
    if(df[column].dtypes==float):
        df[column].fillna(df[column].mean(), inplace=True)
    else:
        df[column].fillna("N/A", inplace=True)

Q. 2) Question ( Based on Value Counts ) Check what are the different types of Make are there in our dataset. And, what is the count (occurrence) of each Make in the data ?

df['Make'].value_counts()

Q. 3) Instruction ( Filtering )Show all the records where Origin is Asia or Europe.

df[df['Origin'].isin(["Asia","Europe"])]

Q. 4) Instruction ( Removing unwanted records ) Remove all the records (rows) where Weight is above 4000.

df[~(df['Weight']>4000)]

Q. 5) Instruction ( Applying function on a column ) Increase all the values of 'MPG_City' column by 3.

df['MPG_City']=df['MPG_City'].apply(lambda x: x+3)



```
