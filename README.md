Q1

 
import pandas as pd

import matplotlib.pyplot as plt

# Check the first few rows to understand the data

print(boston_df.head())

 

# Generate descriptive statistics for 'MEDV' (Median value of owner-occupied homes)

descriptive_stats = boston_df['MEDV'].describe()

print("Descriptive Statistics for Median Value of Owner-Occupied Homes:")

print(descriptive_stats)

 

# Create a boxplot for 'MEDV' (Median value of owner-occupied homes)

plt.figure(figsize=(10, 6))

plt.boxplot(boston_df['MEDV'], vert=False)

plt.title('Boxplot of Median Value of Owner-Occupied Homes')

plt.xlabel('Median Value (in $1000s)')

plt.grid(True)

plt.show()

 

Q2

# Check the first few rows to understand the data

print(boston_df.head())

 

# Create a histogram for 'CHAS' (Charles River variable)

plt.figure(figsize=(10, 6))

plt.hist(boston_df['CHAS'], bins=2, edgecolor='black', alpha=0.7)

plt.title('Histogram of Charles River Variable')

plt.xlabel('Charles River (1 = Near, 0 = Not Near)')

plt.ylabel('Frequency')

plt.xticks([0, 1], ['Not Near', 'Near'])

plt.grid(True)

plt.show()

 

Q3

 
import pandas as pd

import matplotlib.pyplot as plt

 

# Load the dataset from the provided URL

boston_url = 'https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-ST0151EN-SkillsNetwork/labs/boston_housing.csv'

boston_df = pd.read_csv(boston_url)

 

# Check the first few rows to understand the data

print(boston_df.head())

 

# Discretize the 'AGE' variable into three groups

def categorize_age(age):

    if age <= 35:

        return '35 years and younger'

    elif 35 < age <= 50:

        return 'Between 35 and 50 years'

    else:

        return 'Older than 50 years'

 

boston_df['AGE_GROUP'] = boston_df['AGE'].apply(categorize_age)

 

# Create a boxplot for 'MEDV' by 'AGE_GROUP'

plt.figure(figsize=(12, 8))

boston_df.boxplot(column='MEDV', by='AGE_GROUP', grid=False)

plt.title('Boxplot of Median Value of Owner-Occupied Homes by Age Group')

plt.suptitle('')  # Suppress the default title to avoid overlap

plt.xlabel('Age Group')

plt.ylabel('Median Value of Owner-Occupied Homes')

plt.xticks([1, 2, 3], ['35 years and younger', 'Between 35 and 50 years', 'Older than 50 years'])

plt.grid(True)

plt.show()


Q4

# Check the first few rows to understand the data

print(boston_df.head())

 
# Create a scatter plot for 'NOX' (Nitric Oxide Concentrations) vs 'INDUS' (Proportion of Non-Retail Business Acres)

plt.figure(figsize=(10, 6))

plt.scatter(boston_df['INDUS'], boston_df['NOX'], alpha=0.5, edgecolor='k')

plt.title('Scatter Plot of Nitric Oxide Concentrations vs. Proportion of Non-Retail Business Acres')

plt.xlabel('Proportion of Non-Retail Business Acres (INDUS)')

plt.ylabel('Nitric Oxide Concentrations (NOX)')

plt.grid(True)

plt.show()

 
Q5

# Check the first few rows to understand the data

print(boston_df.head())

 
# Create a histogram for 'PTRATIO' (Pupil-to-Teacher Ratio)

plt.figure(figsize=(10, 6))

plt.hist(boston_df['PTRATIO'], bins=20, edgecolor='black', alpha=0.7)

plt.title('Histogram of Pupil-to-Teacher Ratio')

plt.xlabel('Pupil-to-Teacher Ratio')

plt.ylabel('Frequency')

plt.grid(True)

plt.show()

 

Q6


# Solution goes here:

# Compute the Pearson correlation coefficient between 'NOX' and 'INDUS'

correlation = boston_df['NOX'].corr(boston_df['INDUS'])

print(f'Pearson Correlation Coefficient between NOX and INDUS: {correlation}')
