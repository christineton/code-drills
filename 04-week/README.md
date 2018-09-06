## Course Map
### Week Four

-----------------------------------------

### Class Objectives

#### Day One: Class Objectives
* You will be able to serve Jupyter notebook files from local directories and connect to their development environment
* You will be able to create Pandas DataFrames from scratch
* You will understand how to run functions on Pandas DataFrames
* You will know how to read/write DataFrames from/to CSV files using Pandas

#### Day Two: Class Objectives

* You will understand how to navigate through DataFrames using Loc and Iloc
* You will understand how to filter and slice Pandas DataFrames
* You will understand how to create and access Pandas GroupBy objects
* You will understand how to sort DataFrames


#### Day Three: Class Objectives

* You will know how to merge DataFrames together whilst understanding the differences between inner, outer, left, and right merges.
* You will be able to slice data using the cut() method and create new values based upon a series of bins.
* You will feel more confident in their ability to fix Python/Pandas bugs within Jupyter Notebook.
* You will be able to use Google to explore additional Pandas functionality when necessary.


-----------------------------------------

### Week Four | Activities

#### Day One: Activities

* [01-Ins_JupyterIntro](activities/day-1/01-Ins_JupyterIntro)
* [02-Stu_NetflixRemix](activities/day-1/02-Stu_NetflixRemix)
* [03-Ins_IntroToPandas](activities/day-1/03-Ins_IntroToPandas)
* [04-Stu_DataFrameShop](activities/day-1/04-Stu_DataFrameShop)
* [05-Ins_DataFunctions](activities/day-1/05-Ins_DataFunctions)
* [06-Stu_TrainingGrounds](activities/day-1/06-Stu_TrainingGrounds)
* [07-Ins_ColumnManipulation](activities/day-1/07-Ins_ColumnManipulation)
* [08-Stu_Hey_Arnold](activities/day-1/08-Stu_Hey_Arnold)
* [09-Ins_ReadingWritingCSV](activities/day-1/09-Ins_ReadingWritingCSV)
* [10-Stu_GoodReads](activities/day-1/10-Stu_GoodReads)
* [11-Stu_GoodReadsSummary](activities/day-1/11-Stu_GoodReadsSummary)


#### Day Two: Activities

* [01-Ins_LocAndIloc](activities/day-2/01-Ins_LocAndIloc)
* [02-Stu_GoodMovies](activities/day-2/02-Stu_GoodMovies)
* [03-Ins_CleaningData](activities/day-2/03-Ins_CleaningData)
* [04-Par_PortlandCrime](activities/day-2/04-Par_PortlandCrime)
* [05-Par_PandasRecap](activities/day-2/05-Par_PandasRecap)
* [06-Ins_GroupBy](activities/day-2/06-Ins_GroupBy)
* [07-Par_Pokemon](activities/day-2/07-Par_Pokemon)
* [08-Ins_Sorting](activities/day-2/08-Ins_Sorting)
* [09-Stu_SearchForTheWorst](activities/day-2/09-Stu_SearchForTheWorst)



#### Day Three: Activities

* [01-Ins_Merging](activities/day-3/01-Ins_Merging)
* [02-Stu_Cryptocurrency](activities/day-3/02-Stu_Cryptocurrency)
* [03-Ins_Binning](activities/day-3/03-Ins_Binning)
* [04-Stu_TedTalks](activities/day-3/04-Stu_TedTalks)
* [05-Ins_Mapping](activities/day-3/05-Ins_Mapping)
* [06-Stu_CleaningKickstarter](activities/day-3/06-Stu_CleaningKickstarter)
* [07-Ins_IntroToBugfixing](activities/day-3/07-Ins_IntroToBugfixing)
* [08-Stu_BugfixingBonanza](activities/day-3/08-Stu_BugfixingBonanza)


-----------------------------------------

### Week Four | Video Walkthroughs

### Lesson - Training Grounds

Use Pandas to perform analytical actions on the DataFrame provided.
[Watch the Video](https://youtu.be/0WLeu5deL7w)


### Lesson - Search for the Worst

Find the worst player in a position using Pandas.
[Watch the Video](https://youtu.be/-uidknOaiJk)



### Lesson - Cryptocurrency

Analyze the given CSV files using merges.
[Watch the Video](https://youtu.be/7wrl8xZGGDk)


### Homework Solutions

* [PyBank](https://youtu.be/HnwrNrMv03g)

* [PyPoll](https://youtu.be/cdwlWjjwxlc)

* [PyBoss](https://youtu.be/C56qQ5Kg2Dc)

* [PyParagraph](https://youtu.be/ddStyQ-b8co)

-----------------------------------------
### Code Drills

* [Code Drills - Pandas](code-drills)

-----------------------------------------
### Week Four | Slide Deck

* Day 1: None

* Day 2: None

* Day 3: None

-----------------------------------------

### Week Three Homework
- Issued 08/09/2018 | **DUE 08/16/2018** | [Homework](homework)
    * Assignment - Pandas, Pandas, Pandas

-----------------------------------------

### Week Three Terminology

# <span style="color:blue">Introduction to Pandas</span>

Pandas is a Python module that contains structures and functions useful for data exploration and analysis.
The two main data structures Pandas introduces are **Series** and **DataFrames**.

---
## <span style="color:blue">Pandas Series</span>
- 1-D data structure (similar to Python lists, or an Excel column)
- Can contain multiple data types, but usually should contain data of one type
- Create a Pandas Series by passing in a **list** to **pd.Series()**
- By default, a Pandas Series will have an index that starts at 0; can access specific values using this index
- Learn more: https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.html


```python
# Import Pandas module

import pandas as pd
```


```python
# Creating a Pandas Series

my_list = [100, 200, 400, 600, 900]
my_series = pd.Series(my_list)
my_series
```




    0    100
    1    200
    2    400
    3    600
    4    900
    dtype: int64




```python
# Accessing specific values within Series

print(my_series[1]) # will print 200
print(my_series[3]) # will print 600
```

    200
    600


---
## <span style="color:blue">Pandas DataFrames</span>
- 2-D data structure with labeled rows and columns (similar to tables in Excel)
    - For example: if we were looking at traffic violations data for NYC, each row could represent a violation instance, and each column could represent a specific attribution of a violation (date, amount of fine, location, etc.)
- Create a Pandas Dataframe by using **pd.DataFrame()**, and passing in either a **list of dictionaries**, or a **dictionary with lists**
- A lot of data in the real world will be provided in tabular format which can be easily translated into DataFrames
- Learn more: https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html


```python
# Creating a Pandas DataFrame by passing in a LIST OF DICTIONARIES
# Each value in the list is a dictionary
# Imagine that each dictionary represents a row of data in our eventual dataframe
# Each dictionary should have the same keys, since these keys dictate the column headers of our dataframe

my_list = [{"id": 1, "name": "Bob", "account_balance": 500.14},
           {"id": 2, "name": "Amanda", "account_balance": 300.42},
           {"id": 3, "name": "Jill", "account_balance": 943.54},
           {"id": 4, "name": "Dylan", "account_balance": 112.53},
           {"id": 5, "name": "Alex", "account_balance": 895.51}]

my_df_1 = pd.DataFrame(my_list)
my_df_1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>account_balance</th>
      <th>id</th>
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>500.14</td>
      <td>1</td>
      <td>Bob</td>
    </tr>
    <tr>
      <th>1</th>
      <td>300.42</td>
      <td>2</td>
      <td>Amanda</td>
    </tr>
    <tr>
      <th>2</th>
      <td>943.54</td>
      <td>3</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>3</th>
      <td>112.53</td>
      <td>4</td>
      <td>Dylan</td>
    </tr>
    <tr>
      <th>4</th>
      <td>895.51</td>
      <td>5</td>
      <td>Alex</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Re-create the previous Pandas DataFrame, passing in a DICTIONARY WITH LISTS
# The keys of the dictionary represent the column headers of our eventual dataframe
# The lists contain the data for each column

my_dict = {"id": [1, 2, 3, 4, 5],
           "name": ["Bob", "Amanda", "Jill", "Dylan", "Alex"],
           "account_balance": [500.14, 300.42, 943.54, 112.53, 895.51]}

my_df_2 = pd.DataFrame(my_dict)
my_df_2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>account_balance</th>
      <th>id</th>
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>500.14</td>
      <td>1</td>
      <td>Bob</td>
    </tr>
    <tr>
      <th>1</th>
      <td>300.42</td>
      <td>2</td>
      <td>Amanda</td>
    </tr>
    <tr>
      <th>2</th>
      <td>943.54</td>
      <td>3</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>3</th>
      <td>112.53</td>
      <td>4</td>
      <td>Dylan</td>
    </tr>
    <tr>
      <th>4</th>
      <td>895.51</td>
      <td>5</td>
      <td>Alex</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Select a single column from a dataframe by passing in the column's name into square brackets

my_df_2["account_balance"]
```




    0    500.14
    1    300.42
    2    943.54
    3    112.53
    4    895.51
    Name: account_balance, dtype: float64




```python
# You can also select a single column and assign it to another variable

names_col = my_df_2["name"]
names_col
```




    0       Bob
    1    Amanda
    2      Jill
    3     Dylan
    4      Alex
    Name: name, dtype: object




```python
# Now names_col contains only the "names" column

print(names_col[1])
```

    Amanda



```python
# Select multiple columns from a dataframe by passing in a list of the names of the columns

my_df_2[["name", "account_balance"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>account_balance</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bob</td>
      <td>500.14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Amanda</td>
      <td>300.42</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jill</td>
      <td>943.54</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Dylan</td>
      <td>112.53</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alex</td>
      <td>895.51</td>
    </tr>
  </tbody>
</table>
</div>



---
## <span style="color:blue">Important DataFrame Functions</span>
**.head()** returns the first 5 rows of data


```python
# Create a new DataFrame that represents purchase data from an online retailer

my_dict_2 = {"order_id": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13],
             "price": [13.50, 9.99, 12.00, 29.99,
                       14.99, 7.99, 3.49, 10.00,
                       9.99, 17.99, 20.00, 21.00, 14.99],
             "purchase_category": ["Apparel", "Sports", "Toys",
                                   "Apparel", "Apparel", "Household",
                                   "Household", "Toys", "Sports",
                                   "Sports", "Apparel", "Household", "Apparel"],
             "clicked_ad": [True, True, False, True, False,
                            True, True, False, False, True,
                            True, True, False]}
purchase_df = pd.DataFrame(my_dict_2)
```


```python
# Show the first 5 rows of data using .head()
# .head() is great for getting a taste of the data you're dealing with

purchase_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>clicked_ad</th>
      <th>order_id</th>
      <th>price</th>
      <th>purchase_category</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>True</td>
      <td>1</td>
      <td>13.50</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>1</th>
      <td>True</td>
      <td>2</td>
      <td>9.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>3</td>
      <td>12.00</td>
      <td>Toys</td>
    </tr>
    <tr>
      <th>3</th>
      <td>True</td>
      <td>4</td>
      <td>29.99</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>5</td>
      <td>14.99</td>
      <td>Apparel</td>
    </tr>
  </tbody>
</table>
</div>



**.describe()** returns a table of summary statistics on numeric columns in a dataframe


```python
# Note that .describe() will only return summary statistics for your numeric columns
# In this case, statistics for order_id and price columns are returned

purchase_df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>13.00000</td>
      <td>13.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>7.00000</td>
      <td>14.301538</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3.89444</td>
      <td>6.809116</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.00000</td>
      <td>3.490000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>4.00000</td>
      <td>9.990000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>7.00000</td>
      <td>13.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>10.00000</td>
      <td>17.990000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>13.00000</td>
      <td>29.990000</td>
    </tr>
  </tbody>
</table>
</div>



**.mean()** returns the average of all values in a given column or dataframe


```python
# Return the mean of the price column

purchase_df["price"].mean()
```




    14.30153846153846



**.sum()** returns the sum of all values in a given column or dataframe


```python
# Return the sum of all values in the order_id column

purchase_df["order_id"].sum()
```




    91




```python
# These values can also be assigned to variables

mean_price = purchase_df["price"].mean()
sum_order_id = purchase_df["order_id"].sum()

mean_price + sum_order_id
```




    105.30153846153846



**.unique()** returns an array of all of the unique values within a given column


```python
# Returns unique values in the purchase_category column

unique_pcat = purchase_df["purchase_category"].unique()
print(unique_pcat)
print(unique_pcat[2])
```

    ['Apparel' 'Sports' 'Toys' 'Household']
    Toys


**.value_counts()** returns an array containing the # of times each unique value occurs in a given column


```python
# Returns the value counts of each unique value in the purchase_category column

print(purchase_df["purchase_category"].value_counts())
```

    Apparel      5
    Sports       3
    Household    3
    Toys         2
    Name: purchase_category, dtype: int64


---
## <span style="color:blue">Exploring Pandas DataFrames</span>

Two functions exist to make life easier when trying to slice and dice any DataFrame: **.iloc[ ]** and **.loc[ ]**

**.iloc[ ]** uses the *numeric* indexes of a dataframe's rows and columns to return specific values


```python
# Use the purchase_df dataframe created above

purchase_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>clicked_ad</th>
      <th>order_id</th>
      <th>price</th>
      <th>purchase_category</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>True</td>
      <td>1</td>
      <td>13.50</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>1</th>
      <td>True</td>
      <td>2</td>
      <td>9.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>3</td>
      <td>12.00</td>
      <td>Toys</td>
    </tr>
    <tr>
      <th>3</th>
      <td>True</td>
      <td>4</td>
      <td>29.99</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>5</td>
      <td>14.99</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>True</td>
      <td>6</td>
      <td>7.99</td>
      <td>Household</td>
    </tr>
    <tr>
      <th>6</th>
      <td>True</td>
      <td>7</td>
      <td>3.49</td>
      <td>Household</td>
    </tr>
    <tr>
      <th>7</th>
      <td>False</td>
      <td>8</td>
      <td>10.00</td>
      <td>Toys</td>
    </tr>
    <tr>
      <th>8</th>
      <td>False</td>
      <td>9</td>
      <td>9.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>9</th>
      <td>True</td>
      <td>10</td>
      <td>17.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>10</th>
      <td>True</td>
      <td>11</td>
      <td>20.00</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>11</th>
      <td>True</td>
      <td>12</td>
      <td>21.00</td>
      <td>Household</td>
    </tr>
    <tr>
      <th>12</th>
      <td>False</td>
      <td>13</td>
      <td>14.99</td>
      <td>Apparel</td>
    </tr>
  </tbody>
</table>
</div>



There are several possible ways to use **.iloc[ ]**
<br>
The general structure is: **.iloc[*rows you want*, *columns you want*]**
- Use single values to just get one row/column
- Use a colon (:) to get all rows/columns
- Use a list to get specific rows/columns
- Use a range(x:y) to get a range of rows/columns


```python
# To return ALL ROWS and COLUMN 2 (order_id)

purchase_df.iloc[ : , 1]

# The colon before the comma in .iloc[] means we want ALL rows
# The 1 after the comma means we want the column at index 1
```




    0      1
    1      2
    2      3
    3      4
    4      5
    5      6
    6      7
    7      8
    8      9
    9     10
    10    11
    11    12
    12    13
    Name: order_id, dtype: int64




```python
# To return ROWS 1 THROUGH 4 (including 4), and ALL COLUMNS

purchase_df.iloc[0:4, : ]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>clicked_ad</th>
      <th>order_id</th>
      <th>price</th>
      <th>purchase_category</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>True</td>
      <td>1</td>
      <td>13.50</td>
      <td>Apparel</td>
    </tr>
    <tr>
      <th>1</th>
      <td>True</td>
      <td>2</td>
      <td>9.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>3</td>
      <td>12.00</td>
      <td>Toys</td>
    </tr>
    <tr>
      <th>3</th>
      <td>True</td>
      <td>4</td>
      <td>29.99</td>
      <td>Apparel</td>
    </tr>
  </tbody>
</table>
</div>




```python
# To returns ROWS 2, 3, AND 5, and COLUMNS 2 THROUGH 4 (including 4)

purchase_df.iloc[[1, 2, 4], 1:4]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>order_id</th>
      <th>price</th>
      <th>purchase_category</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>9.99</td>
      <td>Sports</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>12.00</td>
      <td>Toys</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>14.99</td>
      <td>Apparel</td>
    </tr>
  </tbody>
</table>
</div>



**.loc[ ]** uses the *named* indexes of a dataframe's rows and columns to return specific values.

The general structure for .loc[] is the same as that for .iloc[], except named indexes are used instead of numeric indexes
<br>
A column's named index is simply its **column name**
<br>
By default, when we create a dataframe, a row's index is numeric and starts at 0. You can set a named index for a dataframe's rows by using **.set_index()**


```python
# Create a new dataframe
example_dict = {"first_name": ["Bill", "James", "Tyler", "Matt", "Jon"],
                "last_name": ["Smith", "Alvarez", "Dant", "May", "Livingston"],
                "age": [25, 34, 52, 26, 43],
                "credit_score": [721, 683, 761, 641, 602]}
credit_df = pd.DataFrame(example_dict)
credit_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>credit_score</th>
      <th>first_name</th>
      <th>last_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>721</td>
      <td>Bill</td>
      <td>Smith</td>
    </tr>
    <tr>
      <th>1</th>
      <td>34</td>
      <td>683</td>
      <td>James</td>
      <td>Alvarez</td>
    </tr>
    <tr>
      <th>2</th>
      <td>52</td>
      <td>761</td>
      <td>Tyler</td>
      <td>Dant</td>
    </tr>
    <tr>
      <th>3</th>
      <td>26</td>
      <td>641</td>
      <td>Matt</td>
      <td>May</td>
    </tr>
    <tr>
      <th>4</th>
      <td>43</td>
      <td>602</td>
      <td>Jon</td>
      <td>Livingston</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Set the row index to be the first_name

credit_df = credit_df.set_index("first_name")
credit_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>credit_score</th>
      <th>last_name</th>
    </tr>
    <tr>
      <th>first_name</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bill</th>
      <td>25</td>
      <td>721</td>
      <td>Smith</td>
    </tr>
    <tr>
      <th>James</th>
      <td>34</td>
      <td>683</td>
      <td>Alvarez</td>
    </tr>
    <tr>
      <th>Tyler</th>
      <td>52</td>
      <td>761</td>
      <td>Dant</td>
    </tr>
    <tr>
      <th>Matt</th>
      <td>26</td>
      <td>641</td>
      <td>May</td>
    </tr>
    <tr>
      <th>Jon</th>
      <td>43</td>
      <td>602</td>
      <td>Livingston</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Now, we can filter this dataframe using .loc[]

# Return data for James' and Tyler's rows, ALL COLUMNS included

credit_df.loc[["James", "Tyler"], : ]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>credit_score</th>
      <th>last_name</th>
    </tr>
    <tr>
      <th>first_name</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>James</th>
      <td>34</td>
      <td>683</td>
      <td>Alvarez</td>
    </tr>
    <tr>
      <th>Tyler</th>
      <td>52</td>
      <td>761</td>
      <td>Dant</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Return rows from Bill to Matt (including Matt), and only the age and credit_score columns

credit_df.loc["Bill":"Matt", ["age", "credit_score"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>credit_score</th>
    </tr>
    <tr>
      <th>first_name</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bill</th>
      <td>25</td>
      <td>721</td>
    </tr>
    <tr>
      <th>James</th>
      <td>34</td>
      <td>683</td>
    </tr>
    <tr>
      <th>Tyler</th>
      <td>52</td>
      <td>761</td>
    </tr>
    <tr>
      <th>Matt</th>
      <td>26</td>
      <td>641</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Return all rows, only the credit_score column

credit_df.loc[ : , "credit_score"]
```




    first_name
    Bill     721
    James    683
    Tyler    761
    Matt     641
    Jon      602
    Name: credit_score, dtype: int64



Remember, you can get the same data you want using either .loc[ ] or .iloc[ ]
<br>
The two functions essentially perform the same task, but with different methods of operation


------------------------------------------------


# <span style="color:blue">Exploring Pandas</span>
Now that we're familiar with Pandas Series and DataFrames, let's delve further into Pandas' more complex capabilities: **grouping**, **sorting**, **merging**, and **binning**. These utilize and build upon the previous concepts we've learned.

---
## <span style="color:blue">Grouping</span>
Pandas has the functionality to group dataframes by unique values in one or multiple columns. This allows for creating informative summaries out of large datasets. For example, if you were analyzing raw census data, grouping would allow you to summarize the data based on *gender* or *age* groupings, or by *city* and *state*.


```python
import pandas as pd
```


```python
# Create a dataframe to demonstrate grouping

raw_dict = {"Vehicle Type": ["Car", "Car", "SUV", "Car", "Truck", "Truck", "SUV", "Truck", "Car", "SUV", "SUV", "Truck"],
            "Manufacturer": ["Ford", "GM", "Ford", "Chevy", "Ford", "Chevy", "GM", "GM", "Ford", "Chevy", "GM", "Chevy"],
            "Owner": ["Bob", "Andrew", "Sally", "Amanda", "Bill", "Mike", "Lindsey", "Kristen", "Matt", "Anna", "Jon", "Erin"],
            "Horsepower": [265, 190, 240, 350, 365, 400, 275, 300, 185, 280, 310, 240],
            "Torque (lb-ft)": [270, 215, 203, 350, 415, 275, 290, 190, 280, 305, 250, 290],
            "Fuel Economy (mpg)": [25, 27, 22, 31, 19, 17, 23, 18, 27, 21, 19, 18]}
vehicles_df = pd.DataFrame(raw_dict)
vehicles_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
  </tbody>
</table>
</div>



To start grouping a dataframe, run the following:
~~~~{.python}
grouped_df = original_df.groupby('column1')
~~~~

<code class="python">.groupby()</code> returns a "GroupBy" object. In the above line of code, <code class="python">grouped_df</code> is what holds the "GroupBy" object. The variable (column name) that you want to group by is passed into <code class="python">.groupby()</code>. In the above line of code, we are grouping <code class="python">original_df</code> by the unique values in column named <code class="python">'column1'</code>.

This "GroupBy" object is not exactly usable or useful in and of itself. However, running data functions on it (i.e. <code class="python">.sum()</code>, <code class="python">.mean()</code>, etc.) will let you extract useful summary statistics for each group.


```python
# Group vehicles_df by the "Vehicle Type" column

grouped_vehicles_df = vehicles_df.groupby("Vehicle Type")

# Note that the "GroupBy" object by itself is not particularly useful

print(grouped_vehicles_df)
```

    <pandas.core.groupby.DataFrameGroupBy object at 0x109cdbc50>


Our `vehicles_df` dataframe contains 12 rows of data. Each row of data represents a specific vehicle model and there are 5 columns, or variables, that describe each model (fuel economy, horsepower, manufacturer, torque, and vehicle type). While this data is useful as is, grouping it lets us extract more insights from it.

So, we've grouped our `vehicles_df` dataframe by `"Vehicle Type"`, and assigned the resultant "GroupBy" object to `grouped_vehicles_df`. While printing this object offers no useful information, We can run data functions on this "GroupBy" object to obtain summary statistics per each group (i.e. Car, Truck, and SUV).

First, let's obtain a count of all values per vehicle type, across all columns:


```python
grouped_vehicles_df.count()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
    </tr>
    <tr>
      <th>Vehicle Type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Car</th>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>



In the above line, we simply ran <code class="python">.count()</code> on our entire "GroupBy" object.

We can also run these data functions on one column, or a select few columns. Now, let's find out the average fuel economy per group:


```python
grouped_vehicles_df["Fuel Economy (mpg)"].mean()
```




    Vehicle Type
    Car      27.50
    SUV      21.25
    Truck    18.00
    Name: Fuel Economy (mpg), dtype: float64



How about the maximum horsepower and torque per group?


```python
grouped_vehicles_df[["Horsepower", "Torque (lb-ft)"]].max()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Horsepower</th>
      <th>Torque (lb-ft)</th>
    </tr>
    <tr>
      <th>Vehicle Type</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Car</th>
      <td>350</td>
      <td>350</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>310</td>
      <td>305</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>400</td>
      <td>415</td>
    </tr>
  </tbody>
</table>
</div>



Note: running a data function on a "GroupBy" object returns a DataFrame (if 2-D), or a Series (if 1-D). Thus, you can create new dataframes based on the results of these data functions


```python
min_power_tq = grouped_vehicles_df[["Horsepower", "Torque (lb-ft)"]].min()
min_power_tq
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Horsepower</th>
      <th>Torque (lb-ft)</th>
    </tr>
    <tr>
      <th>Vehicle Type</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Car</th>
      <td>185</td>
      <td>215</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>240</td>
      <td>203</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>240</td>
      <td>190</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Proving that the result of running data functions on "GroupBy" objects is a dataframe

type(min_power_tq)
```




    pandas.core.frame.DataFrame



One last thing about grouping: **you can group by multiple columns**.

This is useful if you're dealing with demographic data and want to group by city AND state. You can do this by passing in a list that contains the columns you want to group by.


```python
# Group vehicles_df by both Manufacturer AND Vehicle Type

grouped_vehicles_df_2 = vehicles_df.groupby(["Manufacturer", "Vehicle Type"])

# Get averages

grouped_vehicles_df_2.mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Torque (lb-ft)</th>
    </tr>
    <tr>
      <th>Manufacturer</th>
      <th>Vehicle Type</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3" valign="top">Chevy</th>
      <th>Car</th>
      <td>31.0</td>
      <td>350.0</td>
      <td>350.0</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>21.0</td>
      <td>280.0</td>
      <td>305.0</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>17.5</td>
      <td>320.0</td>
      <td>282.5</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">Ford</th>
      <th>Car</th>
      <td>26.0</td>
      <td>225.0</td>
      <td>275.0</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>22.0</td>
      <td>240.0</td>
      <td>203.0</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>19.0</td>
      <td>365.0</td>
      <td>415.0</td>
    </tr>
    <tr>
      <th rowspan="3" valign="top">GM</th>
      <th>Car</th>
      <td>27.0</td>
      <td>190.0</td>
      <td>215.0</td>
    </tr>
    <tr>
      <th>SUV</th>
      <td>21.0</td>
      <td>292.5</td>
      <td>270.0</td>
    </tr>
    <tr>
      <th>Truck</th>
      <td>18.0</td>
      <td>300.0</td>
      <td>190.0</td>
    </tr>
  </tbody>
</table>
</div>



---
## <span style="color:blue">Sorting</span>
Pandas makes it possible to sort by the values in different columns in any dataframe. The main function for this is **<code class="python">.sort_values()</code>**.

Let's sort <code class="python">vehicles_df</code>, from our previous example, by fuel economy:


```python
# First, let's see what the unaltered vehicles_df looks like

vehicles_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Now, let's sort this dataframe by the "Fuel Economy (mpg)" column

vehicles_df.sort_values("Fuel Economy (mpg)")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
    </tr>
  </tbody>
</table>
</div>



Note that <code class="python">.sort_values()</code> sorts ascending (or, from smallest to largest) by default. We can also sort descending by simply passing in <code class="python">ascending=False</code> into <code class="python">.sort_values()</code>


```python
# Sort DESCENDING by the "Fuel Economy (mpg)" column

vehicles_df.sort_values("Fuel Economy (mpg)", ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Creating a new dataframe from the result of running .sort_values()

sorted_df = vehicles_df.sort_values("Fuel Economy (mpg)")
sorted_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
  </tbody>
</table>
</div>



Note that sorting a dataframe does not reset the row indexes. Once you sort a dataframe, it's best practice to reset the row indexes. Use the **<code class="python">.reset_index()</code>** function to do this.


```python
# Run the .reset_index() on the sorted dataframe
# Pass in drop=True to prevent appending a new column with the old indexes to the dataframe

sorted_df = sorted_df.reset_index(drop=True)
sorted_df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>1</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>2</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
  </tbody>
</table>
</div>



---
## <span style="color:blue">Merging</span>
Many times, the data you'll want to analyze comes in the form of several tables. Pandas contains a function called **<code class="python">merge()</code>** that will merge two dataframes together.

In order to merge two dataframes successfully, you'll need to specify a column to merge on. This column should be the link that connects the two dataframe (i.e. some sort of ID column).

Let's go through the different types of merges using two dataframes - one that contains an online retailer's purchase data for the past week, and another one that contains data on customers who've signed up for the email list.


```python
# Create the dataframe containing purchase data

purchase_dict = {"Customer ID": [123, 757, 985, 907, 642, 754, 396, 278],
                 "Order Price": [9.99, 15.00, 7.99, 25.00, 18.00, 31.00, 29.99, 17.99],
                 "Category": ["Clothes", "Electronics", "Toys", "Toys", "Clothes", "Toys", "Electronics", "Clothes"]}
purchase_df = pd.DataFrame(purchase_dict)
purchase_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Customer ID</th>
      <th>Order Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Clothes</td>
      <td>123</td>
      <td>9.99</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Electronics</td>
      <td>757</td>
      <td>15.00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Toys</td>
      <td>985</td>
      <td>7.99</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Toys</td>
      <td>907</td>
      <td>25.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clothes</td>
      <td>642</td>
      <td>18.00</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Toys</td>
      <td>754</td>
      <td>31.00</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Electronics</td>
      <td>396</td>
      <td>29.99</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Clothes</td>
      <td>278</td>
      <td>17.99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create the dataframe containing email list data

email_dict = {"Customer ID": [123, 147, 278, 396, 421, 642, 754],
              "Name": ["Jill", "Tony", "Sarah", "Bill", "Erin", "Tyler", "Amanda"],
              "Email Address": ["jill29@gmail.com", "tony@yahoo.com", "sarah.b@gmail.com", "bill93@gmail.com", "erinm@yahoo.com", "tyler@aol.com", "amanda72@gmail.com"]}
email_df = pd.DataFrame(email_dict)
email_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Customer ID</th>
      <th>Email Address</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>123</td>
      <td>jill29@gmail.com</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>1</th>
      <td>147</td>
      <td>tony@yahoo.com</td>
      <td>Tony</td>
    </tr>
    <tr>
      <th>2</th>
      <td>278</td>
      <td>sarah.b@gmail.com</td>
      <td>Sarah</td>
    </tr>
    <tr>
      <th>3</th>
      <td>396</td>
      <td>bill93@gmail.com</td>
      <td>Bill</td>
    </tr>
    <tr>
      <th>4</th>
      <td>421</td>
      <td>erinm@yahoo.com</td>
      <td>Erin</td>
    </tr>
    <tr>
      <th>5</th>
      <td>642</td>
      <td>tyler@aol.com</td>
      <td>Tyler</td>
    </tr>
    <tr>
      <th>6</th>
      <td>754</td>
      <td>amanda72@gmail.com</td>
      <td>Amanda</td>
    </tr>
  </tbody>
</table>
</div>



Note that the two dataframes share the "Customer ID" column in common. This column is what makes the merge possible.

An **inner merge** joins the two dataframes only where the values in the joining column match. By default, <code class="python">merge()</code> performs an inner merge.


```python
# Performing an inner merge on the two dataframes using the "Customer ID" field
# Pass into merge(): the two dataframes to merge together, as well as the column to merge on
# Note that it only returns the rows where the value in "Customer ID" matched between the two dataframes
# If a row did not contain a match in "Customer ID", it is not returned in the merged dataframe

inner_merge_df = pd.merge(purchase_df, email_df, on="Customer ID")
inner_merge_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Customer ID</th>
      <th>Order Price</th>
      <th>Email Address</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Clothes</td>
      <td>123</td>
      <td>9.99</td>
      <td>jill29@gmail.com</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Clothes</td>
      <td>642</td>
      <td>18.00</td>
      <td>tyler@aol.com</td>
      <td>Tyler</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Toys</td>
      <td>754</td>
      <td>31.00</td>
      <td>amanda72@gmail.com</td>
      <td>Amanda</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Electronics</td>
      <td>396</td>
      <td>29.99</td>
      <td>bill93@gmail.com</td>
      <td>Bill</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clothes</td>
      <td>278</td>
      <td>17.99</td>
      <td>sarah.b@gmail.com</td>
      <td>Sarah</td>
    </tr>
  </tbody>
</table>
</div>



You can think of inner merge we just performed as returning only the orders from customers who've also signed up for the email list. We merge the two dataframes to return only rows where the "Customer ID" value matches (and therefore, appears on both dataframes). Also, the merged dataframe contains all columns from both dataframes.

On the other hand, an **outer merge** joins the two dataframes, even where there isn't a match in the joining column. To perform an outer merge, you must specify it by passing in <code class="python">how="outer"</code> to <code class="python">merge()</code>.


```python
# Performing an outer merge on the two dataframes, again using the "Customer ID" field
# Note that it returns all rows from both dataframes

outer_merge_df = pd.merge(purchase_df, email_df, on="Customer ID", how="outer")
outer_merge_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Customer ID</th>
      <th>Order Price</th>
      <th>Email Address</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Clothes</td>
      <td>123</td>
      <td>9.99</td>
      <td>jill29@gmail.com</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Electronics</td>
      <td>757</td>
      <td>15.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Toys</td>
      <td>985</td>
      <td>7.99</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Toys</td>
      <td>907</td>
      <td>25.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clothes</td>
      <td>642</td>
      <td>18.00</td>
      <td>tyler@aol.com</td>
      <td>Tyler</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Toys</td>
      <td>754</td>
      <td>31.00</td>
      <td>amanda72@gmail.com</td>
      <td>Amanda</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Electronics</td>
      <td>396</td>
      <td>29.99</td>
      <td>bill93@gmail.com</td>
      <td>Bill</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Clothes</td>
      <td>278</td>
      <td>17.99</td>
      <td>sarah.b@gmail.com</td>
      <td>Sarah</td>
    </tr>
    <tr>
      <th>8</th>
      <td>NaN</td>
      <td>147</td>
      <td>NaN</td>
      <td>tony@yahoo.com</td>
      <td>Tony</td>
    </tr>
    <tr>
      <th>9</th>
      <td>NaN</td>
      <td>421</td>
      <td>NaN</td>
      <td>erinm@yahoo.com</td>
      <td>Erin</td>
    </tr>
  </tbody>
</table>
</div>



The outer merge we just performed returns all rows from both dataframes. If a customer who placed an order in the past week *has not* signed up for the email list (i.e. they are in the <code class="python">purchase_df</code> dataframe, but not the <code class="python">email_df</code> dataframe), Pandas fills in the "Name" and "Email Address" fields with null values (<code class="python">NaN</code>). If someone who has signed up for the email list *has not* placed an order in the past week (i.e. they are in the <code class="python">email_df</code> dataframe, but not the <code class="python">purchase_df</code> dataframe), Pandas fills in the "Category" and "Order Price" with null values (<code class="python">NaN</code>).

Lastly, a **right** or **left merge** joins the two dataframes, but only protects the data in one of the dataframes you're joining together. In other words, it's like an outer merge that only applies to one dataframe. With a right or left merge, rows in the *other* dataframe where there isn't a match in the joining column are dropped.

With Pandas, the **first** dataframe you pass into <code class="python">merge()</code> is considered the **left** dataframe, and the **second** dataframe you pass into <code class="python">merge()</code> is considered the **right** dataframe.


```python
# Performing a left merge on the two dataframes
# Here, purchase_df is the left dataframe, and email_df is the right dataframe

left_merge_df = pd.merge(purchase_df, email_df, on="Customer ID", how="left")
left_merge_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Category</th>
      <th>Customer ID</th>
      <th>Order Price</th>
      <th>Email Address</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Clothes</td>
      <td>123</td>
      <td>9.99</td>
      <td>jill29@gmail.com</td>
      <td>Jill</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Electronics</td>
      <td>757</td>
      <td>15.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Toys</td>
      <td>985</td>
      <td>7.99</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Toys</td>
      <td>907</td>
      <td>25.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Clothes</td>
      <td>642</td>
      <td>18.00</td>
      <td>tyler@aol.com</td>
      <td>Tyler</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Toys</td>
      <td>754</td>
      <td>31.00</td>
      <td>amanda72@gmail.com</td>
      <td>Amanda</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Electronics</td>
      <td>396</td>
      <td>29.99</td>
      <td>bill93@gmail.com</td>
      <td>Bill</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Clothes</td>
      <td>278</td>
      <td>17.99</td>
      <td>sarah.b@gmail.com</td>
      <td>Sarah</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Performing a right merge on the two dataframes
# Here, email_df is the left dataframe and purchase_df is the right dataframe

right_merge_df = pd.merge(email_df, purchase_df, on="Customer ID", how="right")
right_merge_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Customer ID</th>
      <th>Email Address</th>
      <th>Name</th>
      <th>Category</th>
      <th>Order Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>123</td>
      <td>jill29@gmail.com</td>
      <td>Jill</td>
      <td>Clothes</td>
      <td>9.99</td>
    </tr>
    <tr>
      <th>1</th>
      <td>278</td>
      <td>sarah.b@gmail.com</td>
      <td>Sarah</td>
      <td>Clothes</td>
      <td>17.99</td>
    </tr>
    <tr>
      <th>2</th>
      <td>396</td>
      <td>bill93@gmail.com</td>
      <td>Bill</td>
      <td>Electronics</td>
      <td>29.99</td>
    </tr>
    <tr>
      <th>3</th>
      <td>642</td>
      <td>tyler@aol.com</td>
      <td>Tyler</td>
      <td>Clothes</td>
      <td>18.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>754</td>
      <td>amanda72@gmail.com</td>
      <td>Amanda</td>
      <td>Toys</td>
      <td>31.00</td>
    </tr>
    <tr>
      <th>5</th>
      <td>757</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Electronics</td>
      <td>15.00</td>
    </tr>
    <tr>
      <th>6</th>
      <td>985</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Toys</td>
      <td>7.99</td>
    </tr>
    <tr>
      <th>7</th>
      <td>907</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Toys</td>
      <td>25.00</td>
    </tr>
  </tbody>
</table>
</div>



---
## <span style="color:blue">Binning</span>
Often times, it's useful to put numeric data into bins. This allows for more vigorous and customizable analysis of datasets. `cut()` is a function in Pandas that gives you the capability of binning data.

Let's work on binning the "Horsepower" values in `vehicles_df`.


```python
# First, call vehicles_df to examine it

vehicles_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create bins and bin labels for the Horsepower column

hp_bins = [180, 200, 350, 400]
hp_labels = ["Slow", "Decent", "Fast"]

# Bin the Horsepower column
# cut() returns a Pandas Series containing each of the binned column's values translated into their corresponding bins

pd.cut(vehicles_df["Horsepower"], hp_bins, labels=hp_labels)
```




    0     Decent
    1       Slow
    2     Decent
    3     Decent
    4       Fast
    5       Fast
    6     Decent
    7     Decent
    8       Slow
    9     Decent
    10    Decent
    11    Decent
    Name: Horsepower, dtype: category
    Categories (3, object): [Slow < Decent < Fast]



The syntax for creating the bins may be a bit confusing at first.

The first argument passed into `cut()` is the dataframe column you'd like to bin.

The second argument passed into `cut()` is a list that is supposed to represent the bins you'd like to create. In the above lines of code, the list `hp_bins` contains four numbers - these numbers represent our **bin edges**. Therefore, when it's passed into `cut()`, Pandas creates **three bins**:
- the first one ranging from **180 to 200**
- the second one ranging from **200 to 350**
- the third one ranging from **350 to 400**..

The third argument passed into `cut()` is a list that contains your bin labels. The list `hp_labels` contains 3 strings. When this list is passed into `cut()`:
- the label **`"Slow"`** is mapped to the bin ranging from **180 to 200**
- the label **`"Decent"`** is mapped to the bin ranging from **200 to 350**
- the label **`"Fast"`** is mapped to the bin ranging from **350 to 400**.


```python
# We can append our bins to vehicles_df

vehicles_df["Speed"] = pd.cut(vehicles_df["Horsepower"], hp_bins, labels=hp_labels)
vehicles_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Fuel Economy (mpg)</th>
      <th>Horsepower</th>
      <th>Manufacturer</th>
      <th>Owner</th>
      <th>Torque (lb-ft)</th>
      <th>Vehicle Type</th>
      <th>Speed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>265</td>
      <td>Ford</td>
      <td>Bob</td>
      <td>270</td>
      <td>Car</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>1</th>
      <td>27</td>
      <td>190</td>
      <td>GM</td>
      <td>Andrew</td>
      <td>215</td>
      <td>Car</td>
      <td>Slow</td>
    </tr>
    <tr>
      <th>2</th>
      <td>22</td>
      <td>240</td>
      <td>Ford</td>
      <td>Sally</td>
      <td>203</td>
      <td>SUV</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31</td>
      <td>350</td>
      <td>Chevy</td>
      <td>Amanda</td>
      <td>350</td>
      <td>Car</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>365</td>
      <td>Ford</td>
      <td>Bill</td>
      <td>415</td>
      <td>Truck</td>
      <td>Fast</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>400</td>
      <td>Chevy</td>
      <td>Mike</td>
      <td>275</td>
      <td>Truck</td>
      <td>Fast</td>
    </tr>
    <tr>
      <th>6</th>
      <td>23</td>
      <td>275</td>
      <td>GM</td>
      <td>Lindsey</td>
      <td>290</td>
      <td>SUV</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>7</th>
      <td>18</td>
      <td>300</td>
      <td>GM</td>
      <td>Kristen</td>
      <td>190</td>
      <td>Truck</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>8</th>
      <td>27</td>
      <td>185</td>
      <td>Ford</td>
      <td>Matt</td>
      <td>280</td>
      <td>Car</td>
      <td>Slow</td>
    </tr>
    <tr>
      <th>9</th>
      <td>21</td>
      <td>280</td>
      <td>Chevy</td>
      <td>Anna</td>
      <td>305</td>
      <td>SUV</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>10</th>
      <td>19</td>
      <td>310</td>
      <td>GM</td>
      <td>Jon</td>
      <td>250</td>
      <td>SUV</td>
      <td>Decent</td>
    </tr>
    <tr>
      <th>11</th>
      <td>18</td>
      <td>240</td>
      <td>Chevy</td>
      <td>Erin</td>
      <td>290</td>
      <td>Truck</td>
      <td>Decent</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Binning adds a new wrinkle to our data, allowing for more vigorous analysis
# For example, we can now group by our bins

grouped_speed_vehicles_df = vehicles_df.groupby("Speed")
grouped_speed_vehicles_df[["Horsepower", "Torque (lb-ft)"]].mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Horsepower</th>
      <th>Torque (lb-ft)</th>
    </tr>
    <tr>
      <th>Speed</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Slow</th>
      <td>187.5</td>
      <td>247.5</td>
    </tr>
    <tr>
      <th>Decent</th>
      <td>282.5</td>
      <td>268.5</td>
    </tr>
    <tr>
      <th>Fast</th>
      <td>382.5</td>
      <td>345.0</td>
    </tr>
  </tbody>
</table>
</div>




### Helpful Links

* [Formatting](https://pyformat.info/)

* [Pandas Tutorials](https://chrisalbon.com/)

* [Pandas Documentation](http://pandas.pydata.org/)

* [Visual Guide to Joins](https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)

* [Pandas Merging](https://pandas.pydata.org/pandas-docs/stable/merging.html)

* [Pandas Cheatseet](https://www.dataquest.io/blog/pandas-cheat-sheet/)

* [Python Data Analysis Library](https://pandas.pydata.org/#python-data-analysis-library)

* [Pandas Describe ](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.describe.html)

* [NameSpace](https://www.python-course.eu/namespaces.php)

* [pandas.DataFrame.drop](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.drop.html)

* [pandas.DataFrame.dropna](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.dropna.html)

* [pandas.DataFrame.loc](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.loc.html)

* [Zen of Python](https://en.wikipedia.org/wiki/Zen_of_Python)


```python
import this
```
```text
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

```

------------------------------------------------


