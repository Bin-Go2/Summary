> Reference : Kaggle Pandas https://www.kaggle.com/learn/pandas
>
### 1. Use pandas

`import pandas as pd`

There are two core objects in pandas:  the `DataFrame` and the `Series`.


DataFrame -> `table` </br>
Series    -> in essence, a single `column` of a DataFrame

#### 2. Create DataFrame and Series Object

```
df = pd.DataFrame(data)
df   # display all the values

# using the head() command, which grabs the first five rows:
df.head()
df.head(n)   #get n rows


pd.DataFrame(
{'Yes': [50, 21], 'No': [131, 2]}
)

parameter:
a dictionary whose keys are the column names, and whose values are a list of entries
=>

|     | Yes | No  |
| --- | --- | --- |
| 0   | 50  | 131 |
| 1   | 21  | 1   |
```



```
pd.DataFrame(
{'Yes': [50, 21], 'No': [131, 2]},
index = ['productA','productB']
)

The list of row labels used in a DataFrame is known as an Index. We can assign values to it by using an index parameter in our constructor:

=>
|          | Yes | No  |
| -------- | --- | --- |
| productA | 50  | 131 |
| productB | 21  | 2   |
```

```
pd.Series([30, 35, 40], index=['2015 Sales', '2016 Sales', '2017 Sales'], name='Product A')

However, a Series does not have a column name, it only has one overall name

=>
2015 Sales    30
2016 Sales    35
2017 Sales    40
Name: Product A, dtype: int64
```

There are some format about the parameter data when creating DataFrame

1.data is a dictionary `{ key1:[],key2:[] }`

`fruit = pd.DataFrame({'Apple':30},{'Banana':40})`

2.data is a neseted list
`fruit = pd.DataFrame([[30,40]],columns=['Apple','Banana'])`

### 3. Read data

>most of the time, we won't actually be creating our own data by hand. Instead, we'll be working with data that already exists.

CSV  -> comma-separated values

`df = pd.read_csv(csv_path,index_col=0)`

use the shape attribute to check how large the resulting DataFrame is :
`df.shape`



### 4.Index/Search data
```
Pandas indexing works in one of two paradigms. The first is index-based selection: selecting data based on its numerical position in the data. iloc follows this paradigm.

1.iloc
# get the data of ith row jth column (i and j begin at 0)

df.iloc[i,j]
df.iloc[i][j]
df.iloc[i][label name of jth ]

#to get a column with iloc, we can do the following:
df.iloc[:,j ]

# it also to pass a list:
# select the first column from just the first, second, and third row
df.iloc[[0, 1, 2], 0]



The second paradigm for attribute selection is the one followed by the loc operator: label-based selection. In this paradigm, it's the data index value, not its position, which matters.

2.loc
df.loc[0, 'game'] # get the data from df where it located in the first row and its column's label is game


3.conditional selection
df.loc[df.game == 'LOL']

```






