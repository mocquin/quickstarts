# Introspect
## introspect Series
 - `s.describe()` : return descriptive statistics (min/max/count/mean/std/…)
 - `s.unique()` : list unique values in serie
 - `s.value_counts()` : histogram

## introspect Dataframe  
 - `df.describe()` : return descriptive statistics (min/max/count/mean/std/…)
 - `df2.dtypes` : data types of cols
 - `df.head()` : print head top of df
 - `df.tail()` : print tail end of df
 - `df.index`: show the index column
 - `df.column` : show the columns name
 - `df.mean()` : mean of cols
 - `df.shape` : number of row and cols
 - `df[“TCN”].unique()` : List different values
 - `df[“w”].nunique()` : number of unique values
 - `for index, row in df.iterrows(): print(row['c1'], row['c2'])` : loop over rows
 
 
# Merge/concat 
Concat and merge are the main functions. Join and append are shortcuts.

## merge
Use merge when data is relevant for the merging
 - Default merge : how=”inner” : Inner merge : merge columns and only keep rows that appear in both df (intersect columns names, keep rows where the values of these columns overlap)
 - By default, will use all columns name that overlap :  on=None, equivalent to on=[list of all columns names that are in both df”]
 - How=”outer” : keep all rows, adding Nan where values are missing
 - pd.merge(df1, df2, how="left") : keep all rows of left df, and add data to rows that appear in right df (output has same length as left df)
 - Concatenate df col-wise (augment) : pd.merge(left_df, right_df, on='A') (defaults to inner merge)

## concatenate
merge df without comparing data
 - Concatenate df row-wise (pile): pd.concat([df1, df2]), equivalent to axis=0
 - Concatenate df column-wise (augment) : pdf.concat([df1, df2], axis=1)
 - Ignore_index=False by default will keep index from both df. Ignore_index=True will create new index for output df
 - Join=”outer” by default will keep all data and fill missing with nan. Join=’inner” will only keep columns that appear in both df
  
## other tools for merging
 - Join : on=None by default will join index-wise
 - df1.join(df2) : augment column-wise
 - If some columns have same name, use suffix to explicitly precise which is from where : Df1.join(df2, lsuffix=”_x”)
 - Append data : df = df.append({"firstname": "John", "lastname":"Johny"}, ignore_index=True) # careful, not in-place append
 

# Subselection
## subselection based on values
 - Select single cols : `df[“A”]`
 - Select rows : `df[0:3]`
 - Select multiple cols : `df.loc[:, ['A', 'B']]`
 - Select multiple cols and index : `df.loc['20130102':'20130104', ['A', 'B']]`
 - Select with multiple conditions : `df.loc[(df['A'] >= 0) & (df['B'] <= 10)`
 - Select with condition, only some columns : `df.loc[df['a'] > 10, ['a','c']]` (with parent’s!)
 - Select single value : `df.at[dates[0], 'A']` (equivalent to `df.loc[dates[0], 'A']`)

## subselection based on index
 - Select rows by index : `df.iloc[3]`
 - Select rows and cols by index : `df.iloc[3:5, 0:2]`
 - Select single value based on index : `df.iat[1, 1]` (equivalent to `df.iloc[1, 1]`)

## subselection boolean based on condition
 - Numerical value on all df: `df[df > 0]`
 - Numerical value on col : `df[df['A'] > 0]`
 - Select specific values : `df2[df2['E'].isin(['two', 'four'])]` (select rows where “E” col equals two or four)

# Setting
 - Set value by label : df.at[dates[0], 'A'] = 0
 - Set value by position : df.iat[0, 1] = 0

# Apply
 - function to cols :  df.apply(np.cumsum) 
 - function to cols : df.apply(lambda x: x.max() - x.min())

# Modify
 - df.sort_index(axis=1, ascending=False) : sort data by columns name
 - df.sort_values(by='B') : sort data by columns values

Add data : df.loc['y'] = pandas.Series({'a':1, 'b':5, 'c':2, 'd':3})
Modify index : 
 - df.index += 1
 - df.index = range(1,len(df)+1)

Remove rows:
 - df = df.iloc[3:]
 
Remove/extract cols :
 - sub_cols = [“A”, “B”]
 - sub_df = df.loc[:, sub_cols]
 - df.iloc[:, 1:9])
 - df.drop(columns=['Length','Height']) 



# Creation
 - Serie creation : `S = pd.Series(my_list)`
 - empty dataframe : `df = pd.DataFrame(columns=['A','B','C'])`
 - from numpy array : `pd.DataFrame(data_np_array, index=index_list, columns=[“A”, “B”, “C”])`
 - from dict : `df2 = pd.DataFrame({'A': 1.,'B':pd.Timestamp('20130102'),'C': pd.Series(1,index=list(range(4)), dtype='float32'),'E': pd.Categorical(["test", "train", "test", "train"]), 'F': 'foo'})`

 

 
# Plotting
## basic plots
 - histogram a Serie : `boston_df['AGE'].plot.hist(bins=10)`
 - plot a df : `df.plot()`
 - `df.plot(x ='Unemployment_Rate', y='Stock_Index_Price', kind = 'scatter')` #line, bar
 - `ax = df.plot(x=”x”, y=”y1”, color=”blue”, kind=”scatter”); df.plot(x=”x”, y=”y2”, color=”blue”, kind=”scatter”)`
 - `df.boxplot(by ='day', column =['total_bill'])`
 - `df.boxplot(by ='day', column =['total_bill', 'discount'])`

## multi 2d plots
 - plot scatter matrix : `pd.plotting.scatter_matrix(df)`
 - heatmap correlation matrix : `sns.heatmap(df.corr(), annot=True)`
 
# Others

## Helper functions

### plots y(x) for zs
```python
def plot_xyz(x, y, z, df):
    y_min = min(df[y])
    y_max = max(df[y])
    z_list = df[z].unique()
    n = len(z_list)
    fig, ax = plt.subplots(1, n)
    for n, z_val in enumerate(z_list):
        df[df[z] == z_val].plot(x=x, y=y,
                                kind=”scatter”, ax=ax[n],
                                label=str(z)+”=”+str(z_val))
    plt.legend()
```
 
 


# interactive pandas
## using ipywidgets
[source](https://towardsdatascience.com/interactive-controls-for-jupyter-notebooks-f5c94829aee6)
```python
import ipywidgets as widgets
from ipywidgets import interact, interact_manual
import pandas as pd

# getting some data
import seaborn as sns
df = sns.load_dataset('iris')

# exemple 1 : version 1
@interact
def show_articles_more_than(column='sepal_length', x=5):
    return df.loc[df[column] > x]
    
# exemple 1 : version 2 
# Interact with specification of arguments
@interact
def show_articles_more_than(column=['sepal_length', 'petal_length', 'sepal_width', 'petal_width'], 
                            x=(10, 100000, 10)):
    return df.loc[df[column] > x]

# exemple 2
@interact
def correlations(column1=list(df.select_dtypes("number").columns),
                 column2=list(df.select_dtypes("number").columns)):
    print(f"Correlation: {df[column1].corr(df[column2])}")
    
# exemple 3 : version 1 : automatic update
@interact
def scatter_plot(x=list(df.select_dtypes('number').columns), 
                 y=list(df.select_dtypes('number').columns)[1:]):
    df.plot(kind='scatter', x=x, y=y,
            title=f'{y.title()} vs {x.title()}')

# exemple 3 : version 2 : click to update
@interact_manual
def scatter_plot(x=list(df.select_dtypes('number').columns), 
                 y=list(df.select_dtypes('number').columns)[1:]):
    df.plot(kind='scatter', x=x, y=y,
            title=f'{y.title()} vs {x.title()}')

```



ressources : 
https://towardsdatascience.com/interactive-controls-for-jupyter-notebooks-f5c94829aee6