# Working with Pandas Dataframes

## Read CSV file into Dataframe
```
import pandas as pd

df = pd.read_csv('winequality-red.csv', sep=';')
df.head()
```
The output will display the first 5 rows and header of the dataframe.


## Loop through list of columns in a dataframe
```
new_df = df.rename(columns={'fixed acidity': 'fixed_acidity',
                             'volatile acidity': 'volatile_acidity',
                             'citric acid': 'citric_acid',
                             'residual sugar': 'residual_sugar',
                             'free sulfur dioxide': 'free_sulfur_dioxide',
                             'total sulfur dioxide': 'total_sulfur_dioxide'
                            })
new_df.head()
```

Or a better refactored version to rename column headers
```
new_df = df.rename(columns=lambda x: x.replace(' ', '_'))
new_df.head()

# OR
df.columns = [label.replace(' ', '_') for label in df.columns]
df.head()

```
The output will display the new header labels and first 5 rows of the dataframe.


## Get the median of a column
```
df.column_name.median()

```

Expanded usage from AWS ML course:
```
median_citric_acid = df.citric_acid.median()

for i, citric_acid in enumerate(df.citric_acid):
    if citric_acid >= median_citric_acid:
        df.loc[i, 'citric_acid'] = 'high'
    else:
        df.loc[i, 'citric_acid'] = 'low'
df.groupby('citric_acid').quality.mean()
```


## Refactor AWS ML Example
```
import pandas as pd
df = pd.read_csv('winequality-red.csv', sep=';')

# Re-name column headers to remove whitespace
new_df = df.rename(columns=lambda x: x.replace(' ', '_'))
new_df.head()

median_alcohol = new_df.alcohol.median()
median_pH = new_df.pH.median()
median_sugar = new_df.residual_sugar.median()
median_citric_acid = new_df.citric_acid.median()

params = {'alcohol': median_alcohol, 'pH': median_pH, 'residual_sugar': median_sugar, 'citric_acid': median_citric_acid}

for quality_name, median_quality in params.items():
    for i, param in enumerate(new_df[quality_name]):
        if param >= median_quality:
            new_df.loc[i, [quality_name]] = 'high'
        else:
            new_df.loc[i, [quality_name]] = 'low'
    new_df.groupby([quality_name]).quality.mean()
```


## To get all features
```
def numeric_to_buckets(df, column_name):
    median = df[column_name].median()
    for i, val in enumerate(df[column_name]):
        if val >= median:
            df.loc[i, column_name] = 'high'
        else:
            df.loc[i, column_name] = 'low'

for feature in df.columns[:-1]:
    numeric_to_buckets(df, feature)
    print(df.groupby(feature).quality.mean(), '\n')
```


## Find common elements in two lists
`recent_coding_books = np.intersect1d(coding_books, recent_books) `
NOTE: Using list and set in Python is faster!


## Filter and manipulate array values
```
gift_sum = np.sum(gift_costs[gift_costs < 25])
total_price =  np.sum(new_arr) * 1.08  # Gift tax is 1.08

print(total_price)
```


Or more optimized:
```
total_price = (gift_costs[gift_costs < 25]).sum() * 1.08
print(total_price)
```






