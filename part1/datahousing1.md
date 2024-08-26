---
type: page
title: Data Housing overview
author: A.Belcaid
permalink: /datahousing1/
---

<p align="center">
  <img src="{{ site.baseurl }}/static_files/kaggle_housing_logo.png" alt="House Prices Dataset">
</p>

Welcome to the homework assignment on the classic House Prices dataset from Kaggle! In this assignment, you will explore the dataset, visualize some of its features, and gain insights into the factors affecting house prices.

## Objectives
1. Understand the problem statement and the dataset.
2. Visualize important features and their relationships with the target variable (SalePrice).
3. Perform basic data analysis to derive insights.

## Problem Statement
You are provided with a dataset containing various features of houses and their sale prices. Your task is to analyze these features to understand how they influence the sale prices and build a model to predict house prices.

## Dataset Description
The dataset contains 81 columns, including the target variable `SalePrice`. Here's a brief description of some of the important columns:

- `SalePrice`: The sale price of the house (target variable).
- `OverallQual`: Overall material and finish quality.
- `GrLivArea`: Above grade (ground) living area square feet.
- `GarageCars`: Size of garage in car capacity.
- `TotalBsmtSF`: Total square feet of basement area.
- `FullBath`: Full bathrooms above grade.
- `YearBuilt`: Original construction date.
- `YearRemodAdd`: Remodel date.

For a full list of features, refer to the [data dictionary](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data).

## Instructions

### 1. Data Exploration
First, let's explore the dataset. Load the dataset and display the first few rows to understand its structure.

```python
import pandas as pd

# Load the dataset
data = pd.read_csv('train.csv')

# Display the first few rows
data.head()
```


### 2. Summary Statistics
Generate summary statistics for the numerical features to get an overview of the data distribution.

```python
# Summary statistics for numerical features
data.describe()
```


### 3. Data Visualization
Visualizing data helps in understanding the relationships between features and the target variable. Let's create some visualizations.

#### 3.1 SalePrice Distribution
Plot the distribution of the `SalePrice` to understand its spread and central tendency.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Distribution plot for SalePrice
plt.figure(figsize=(10, 6))
sns.histplot(data['SalePrice'], kde=True)
plt.title('Distribution of SalePrice')
plt.xlabel('SalePrice')
plt.ylabel('Frequency')
plt.show()
```

<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/housing_disribution.png" alt="House Prices Dataset">
</p>

#### 3.2 Correlation Heatmap
Create a heatmap to visualize the correlation between numerical features and `SalePrice`.

```python
# Select the target variable and 5 numerical features
features = ['SalePrice', 'OverallQual', 'GrLivArea', 'GarageCars', 'TotalBsmtSF', 'YearBuilt']
selected_data = data[features]

# Compute the correlation matrix
corr_matrix = selected_data.corr()

# Plot the correlation heatmap
plt.figure(figsize=(10, 6))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Heatmap of Selected Features')
plt.show()
```

<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/heatmap.png" alt="House Prices Dataset">
</p>


#### 3.3 Scatter Plots
Generate scatter plots for some of the key features against `SalePrice`.

```python
# Scatter plot for OverallQual vs SalePrice
plt.figure(figsize=(10, 6))
sns.scatterplot(x='OverallQual', y='SalePrice', data=data)
plt.title('OverallQual vs SalePrice')
plt.xlabel('OverallQual')
plt.ylabel('SalePrice')
plt.show()

# Scatter plot for GrLivArea vs SalePrice
plt.figure(figsize=(10, 6))
sns.scatterplot(x='GrLivArea', y='SalePrice', data=data)
plt.title('GrLivArea vs SalePrice')
plt.xlabel('GrLivArea')
plt.ylabel('SalePrice')
plt.show()
```

<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/sale_overalQual.png" alt="House Prices Dataset">
</p>


<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/sale_GrLivArea.png" alt="House Prices Dataset">
</p>


### 4. Feature Analysis
Analyze the impact of some categorical features on `SalePrice`.

#### 4.1 Box Plots
Create box plots to visualize the distribution of `SalePrice` across different categories.

```python
# Box plot for OverallQual
plt.figure(figsize=(10, 6))
sns.boxplot(x='OverallQual', y='SalePrice', data=data)
plt.title('SalePrice by OverallQual')
plt.xlabel('OverallQual')
plt.ylabel('SalePrice')
plt.show()

# Box plot for YearBuilt
plt.figure(figsize=(10, 6))
sns.boxplot(x='YearBuilt', y='SalePrice', data=data)
plt.title('SalePrice by YearBuilt')
plt.xlabel('YearBuilt')
plt.ylabel('SalePrice')
plt.xticks(rotation=90)
plt.show()
```

<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/price_by_overalQual.png" alt="House Prices Dataset">
</p>

<p align="center">
  <img src="{{ site.baseurl }}/static_files/homework1/price_by_yearbuilt.png" alt="House Prices Dataset">
</p>

## Try It Yourself

Now it's your turn! Answer the following questions by modifying the code snippets provided earlier.


1. Generate a correlation heatmap for the following features: `SalePrice`, `OverallCond`, `YearRemodAdd`, `MasVnrArea`, and `Fireplaces`.
2. Create a scatter plot for `YearBuilt` vs `SalePrice`.
3. Generate summary statistics for the features `LotArea`, `OverallQual`, `TotalBsmtSF`, `FullBath`, and `GarageCars`.
4. Create a box plot to visualize the distribution of `SalePrice` by `FullBath`.
5. Plot the distribution of the `GrLivArea` feature.

Try modifying the code and observe how the visualizations and summaries change with different features. This will help you gain a deeper understanding of the dataset and the factors influencing house prices.

