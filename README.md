# Task15
Overview
This task introduces the Pandas DataFrame, the main table-like data structure used in Python for data analysis.
Objective
Create DataFrames manually and from a dataset, then inspect rows, columns, dimensions, data types, and summary statistics.
Tools Required
Python 3
Pandas
Jupyter Notebook (or Google Colab / another Python environment)
1. Install and import Pandas
If Pandas is not already installed, run:
pip install pandas
Import the library:
import pandas as pd
2. Create a DataFrame manually
A DataFrame can be created from a Python dictionary. Each dictionary key becomes a column.
import pandas as pd

data = {
    "Name": ["Anu", "Ravi", "Sita", "Kiran"],
    "Age": [20, 21, 19, 22],
    "Course": ["Data Science", "AIML", "Data Science", "CSE"],
    "Marks": [85, 90, 88, 78]
}

df = pd.DataFrame(data)

print(df)
3. Inspect the DataFrame
# Display the first five rows
print(df.head())

# Display the last five rows
print(df.tail())

# Display the number of rows and columns
print("Shape:", df.shape)

# Display column names
print("Columns:", df.columns)

# Display data types and non-null counts
df.info()

# Display summary statistics for numerical columns
print(df.describe())
4. Load a real dataset
Option A: Load a CSV file
Download a dataset such as the Titanic dataset and place the CSV file in the same folder as your notebook. Then run:
titanic_df = pd.read_csv("titanic.csv")

print(titanic_df.head())
print("Shape:", titanic_df.shape)
print("Columns:", titanic_df.columns)
titanic_df.info()
print(titanic_df.describe())
Make sure the filename and path match the CSV file you downloaded.
Option B: Use the Iris dataset
If you do not have a CSV file, you can load the Iris dataset using scikit-learn:
pip install scikit-learn
from sklearn.datasets import load_iris
import pandas as pd

iris = load_iris()

iris_df = pd.DataFrame(
    iris.data,
    columns=iris.feature_names
)

iris_df["species"] = [
    iris.target_names[i] for i in iris.target
]

print(iris_df.head())
print("Shape:", iris_df.shape)
print("Columns:", iris_df.columns)
iris_df.info()
print(iris_df.describe())
5. Important Pandas methods
Method / Attribute   Purpose
pd.DataFrame()     Creates a DataFrame pd.read_csv()      Loads data from a CSV file head()             Displays the first five rows by default tail()             Displays the last five rows by default shape              Returns the number of rows and columns columns            Returns the column names info()             Shows column data types and non-null counts describe()         Gives summary statistics for numerical columns
6. Expected Deliverables
A DataFrame created manually from a dictionary.
A real dataset loaded into a DataFrame.
The first rows of the dataset displayed.
The shape and column names displayed.
Data types and summary statistics inspected.
7. Conclusion
In this task, I learned how to create Pandas DataFrames from dictionaries and datasets. I also learned to inspect rows, columns, shape, data types, and numerical summary statistics using common Pandas methods.
