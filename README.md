# sqlite_database_operations
HHA 504 HW  Week 3: Introduction to the world of databases, starting with SQLite. Integrate data processing with Python, utilize Pandas for exploratory data analysis, and conduct database operations using SQLite.

## Datasets
The datasets I chose were pricing transparency datasets from two hospital systems: Stony Brook Hospital and New York Presbyterian

## 1. Data Exploration and Analysis: 
* After loading the necessary packages, I loaded each of the datasets. The Stony Brook dataset was a CSV file while the New York Presbyterian dataset was a JSON file.  
* I used ```df_sbu = pd.read_csv``` and ```df_nyp = pd.read_json``` to load in each of the datasets.
* Summary statistics for each of the dataset's numerical columns were gathered using ```.describe```.
* From the summary statistics and specifically looking at the 'Gross Charge' column from SBU and the "gross charges' column from NYP, an insight can be made that on average, medical services at New York Presbyterian appear to be more expensive than those at Stony Brook.
*  ```value_counts()```  was used to find the frequency counts for the 'Gross Charges' and 'Gross charge' columns for SBU's and NYP's data frames.
*  ```.isnull().sum()``` code was used to check for missing values. There was a significant amount of missing values within Stony Brook's dataset.
*  Each of the dataset columns was then cleaned.


## 2. SQLite Database Operations: 
* First I created a local database named health.db:
```
   conn = sqlite3.connect('health.db')    
   c = conn.cursor()
```
* For the Stony Brook Hospital data, a table named Stony_Brook was created with the following columns:
```
patient_name (Text)
diagnosis (Text)
insurance_accepted (Text)
hospital_charge (Numerical)
patient_cost (Numerical)
``` 
* Sample data was manually inserted into the Stony_Brook table. 
* Data from the (df_sbu) was automatically imported into the SQLite database using Pandas' to_sql method.



