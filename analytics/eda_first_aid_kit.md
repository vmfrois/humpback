# First Aid Kit for Analytics

   - [Initial Data Loading](#initial-data-loading)
   - [Check the Structure and Missing Values](#check-the-structure-and-missing-values)
   - [Basic Statistical Summary](#basic-statistical-summary)
   - [Fill Missing Values](#fill-missing-values)
   - [Drop Missing Values](#drop-missing-values)
   - [Histogram for Numeric Columns](#histogram-for-numeric-columns)
   - [Count Plot for Categorical Columns](#count-plot-for-categorical-columns)
   - [Correlation Heatmap](#correlation-heatmap)
   - [Scatter Plot for Two Variables](#scatter-plot-for-two-variables)
   - [Get Unique Values of a Column](#get-unique-values-of-a-column)
   - [Group By and Calculate Mean](#group-by-and-calculate-mean)
   - [Cross Tabulation of Categorical Variables](#cross-tabulation-of-categorical-variables)
   - [Apply Function to Create New Column](#apply-function-to-create-new-column)
   - [Show Plots](#show-plots)

<br />

## Initial Data Loading
Aqui basicamente estamos importando o `pandas` e atribuindo ele a uma variavel `pd`, com isso usamos o metodo `read_csv` para ler um arquivo `.csv` e transforma-lo em um `Dataframe`
```python
import pandas as pd

# Carregamento dos dados
df = pd.read_csv('path')
```

<br />

## Check the Structure and Missing Values
```python
data.info()
data.isnull().sum()
```

<br />

## Basic Statistical Summary
```python
data.describe()
```

<br />

## Fill Missing Values
```python
data['column'].fillna(value)

#example
data['age'].fillna(data['age'].median(), inplace=True)
```

<br />

## Drop Missing Values
```python
data.dropna()

#example
data_cleaned = data.dropna()
```

<br />

## Histogram for Numeric Columns
```python
sns.histplot(data['column'])
sns.histplot(data['salary'])
plt.show()
```

<br />

## Count Plot for Categorical Columns
```python
sns.countplot(data['column'])
sns.countplot(data['job_title'])
plt.show()
```

<br />

## Correlation Heatmap
```python
sns.heatmap(data.corr(), annot=True)
plt.figure(figsize=(10, 6))
sns.heatmap(data.corr(), annot=True, cmap='coolwarm')
plt.show()
```

<br />

## Scatter Plot for Two Variables
```python
sns.scatterplot(x='column1', y='column2', data=data)

sns.scatterplot(x='age', y='salary', data=data)
plt.show()
```

<br />

## Get Unique Values of a Column
```python
data['column'].unique()

print(data['job_title'].unique())
```

<br />

## Group By and Calculate Mean
```python
data.groupby('column').mean()

print(data.groupby('department')['salary'].mean())
```

<br />

## Cross Tabulation of Categorical Variables
```python
pd.crosstab(data['column1'], data['column2'])
print(pd.crosstab(data['department'], data['job_title']))
```

<br />

## Apply Function to Create New Column
```python
data['new_column'] = data['column'].apply(lambda x: ...)

# Create a new column 'salary_category' based on salary values
data['salary_category'] = data['salary'].apply(lambda x: 'high' if x > 50000 else 'low')

```

<br />

## Show Plots
```python
plt.show()
```
<br />
