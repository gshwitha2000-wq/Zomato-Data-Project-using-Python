# 🍽️ Zomato Data Analysis

## 📌 Project Overview

This project performs an **Exploratory Data Analysis (EDA)** on Zomato restaurant data to understand restaurant types, customer ordering preferences, approximate dining costs, customer votes, and table-booking behavior.

The analysis is performed using **Python, Pandas, NumPy, Matplotlib, and Seaborn**. Different charts are created to identify patterns and compare restaurant categories.

## 🎯 Objectives

The main objectives of this project are:

* Explore and understand the Zomato restaurant dataset.
* Check for duplicate and missing records.
* Examine the different types of restaurants.
* Analyze whether customers prefer online or offline orders.
* Compare the approximate cost for two people across restaurant types.
* Identify which restaurant type receives the highest number of votes.
* Analyze table-booking preferences.
* Visualize the findings using different plots.

## 📂 Dataset

The project uses the following dataset:

```text
Zomato-data-.xls
```

The dataset contains restaurant-related information such as:

| Column                        | Description                                    |
| ----------------------------- | ---------------------------------------------- |
| `listed_in(type)`             | Type/category of restaurant                    |
| `online_order`                | Whether online ordering is available/preferred |
| `approx_cost(for two people)` | Approximate cost for two people                |
| `votes`                       | Number of votes received by the restaurant     |
| `book_table`                  | Whether table booking is available/preferred   |

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook**

## 🔍 Data Exploration

### 1. Importing Libraries

The project begins by importing the required libraries:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Loading the Dataset

The dataset is loaded using Pandas:

```python
df = pd.read_csv('Zomato-data-.xls')
```

### 3. Checking Dataset Columns

The available columns are examined using:

```python
df.columns
```

### 4. Checking Duplicate Records

Duplicate records are checked using:

```python
df.duplicated().sum()
```

### 5. Checking Missing Values

Missing values are identified using:

```python
df.isnull().sum()
```

### 6. Dataset Information

The `info()` function is used to understand the dataset structure and data types:

```python
df.info()
```

### 7. Descriptive Statistics

Statistical information is generated using:

```python
df.describe()
```

### 8. Dataset Shape

The number of rows and columns is checked using:

```python
df.shape
```

## 📊 Exploratory Data Analysis

### 1. Different Types of Restaurants

The project identifies the different restaurant categories using:

```python
df_restaurants = df['listed_in(type)'].unique()
print(df_restaurants)
```

A count plot is then created to visualize the number of restaurants in each category:

```python
sns.countplot(
    x='listed_in(type)',
    data=df
)
```

This provides an overview of the distribution of restaurant types in the dataset.

### 2. Online vs Offline Orders

The project analyzes customer ordering preferences using:

```python
df_orders = df.online_order.value_counts()
print(df_orders)
```

A count plot is used to visualize the results:

```python
sns.countplot(
    x='online_order',
    data=df
)
```

**Finding:** Offline orders are preferred more according to the analysis performed in the notebook.

### 3. Approximate Cost for Two People

The approximate cost for two people is grouped by restaurant type:

```python
df_relationship = df.groupby(
    'listed_in(type)'
)['approx_cost(for two people)'].sum() \
    .sort_values(ascending=True) \
    .reset_index()

print(df_relationship)
```

The results are visualized using a bar chart:

```python
sns.barplot(
    x='listed_in(type)',
    y='approx_cost(for two people)',
    data=df_relationship
)
```

**Finding:** The approximate cost for two people is higher for **Dining** restaurants.

### 4. Restaurant Type with the Most Votes

The total number of votes is calculated for each restaurant type:

```python
df_votes = df.groupby(
    'listed_in(type)'
)['votes'].sum() \
    .sort_values(ascending=False) \
    .reset_index()

print(df_votes)
```

The results are visualized using:

```python
sns.barplot(
    x='listed_in(type)',
    y='votes',
    data=df_votes
)
```

**Finding:** **Dining** type restaurants have received the highest number of votes.

### 5. Table Booking Analysis

The project analyzes whether customers book tables:

```python
df_book_table = df['book_table'].value_counts()
print(df_book_table)
```

A count plot is used:

```python
sns.countplot(
    x='book_table',
    data=df
)
```

**Finding:** The number of people who **do not book a table** is higher.

## 📈 Visualizations

The project contains the following visualizations:

1. Restaurant type distribution.
2. Online vs offline order preference.
3. Approximate cost for two people by restaurant type.
4. Total votes by restaurant type.
5. Table booking preference.

These visualizations make it easier to understand restaurant and customer behavior.

## 💡 Key Insights

Based on the analysis performed in the notebook:

* Different types of restaurants are represented in the dataset.
* **Offline orders are preferred more** than online orders.
* **Dining restaurants** have a higher approximate cost for two people.
* **Dining restaurants** receive more votes than other restaurant types.
* More customers **do not book tables** compared with those who do.

## 📁 Project Structure

```text
Zomato-Data-Analysis/
│
├── Zomato Data Project.ipynb
├── Zomato-data-.xls
└── README.md
```

## ▶️ How to Run the Project

### 1. Clone the Repository

```bash
git clone <your-github-repository-url>
```

### 2. Navigate to the Project Folder

```bash
cd Zomato-Data-Analysis
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the Notebook

Open:

```text
Zomato Data Project.ipynb
```

Make sure the dataset is available in the same directory:

```text
Zomato-data-.xls
```

## 💼 Skills Demonstrated

This project demonstrates practical knowledge of:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Data Exploration
* Data Cleaning
* Missing Value Analysis
* Duplicate Detection
* GroupBy Operations
* Aggregation
* Data Filtering
* Exploratory Data Analysis
* Data Visualization
* Business Insights

## 👩‍💻 Author

**Ashwitha Gogikar**

Data Analytics | Python | Power BI | Machine Learning

* GitHub: https://github.com/gshwitha2000-wq
* LinkedIn: https://www.linkedin.com/in/ashwitha-gogikar-35839a1b5/
