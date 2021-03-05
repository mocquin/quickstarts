
# Common recipies
 - Basic map on condition (ex:string operation) : `def func(age):return "old" if age>99 else "young"; df[“kind”] = df[“age”].map(func)`
 - count unique pair of columns : `d.groupby(['ip', 'useragent']).size()`
 - group by feature and compute mean : `my_df.groupby('age')['height'].mean()`
 - get dropped rows after merging : `merged_df[merged _df['_merge'] != 'both']` use outer merge with indicator=True, then print()
 - rename columns with dict look up : `df.rename(columns={'oldName1': 'newName1', 'oldName2': 'newName2'}, inplace=True)`
 - apply function to row : `appiled_df = df.apply(lambda row: function_toto(row["age)"], row['weight']), axis='columns', result_type='expand')`
 - concatenate column-wise : `df = pd.concat([df, appiled_df], axis='columns')`
 - convert all columns to numeric dtype : `df = df.apply(pd.to_numeric)`
 - convert some columns to numeric dtype : `df[["a", "b"]] = df[["a", "b"]].apply(pd.to_numeric)`
 - convert df to dict : `df.set_index(“key for dict”).T.to_dict()`
 - add columns based on dict lookup : `df['D'] = df['U'].map(d)`
 - subselection columns : `df[[“A”, “B”, “D”]]` 
 - inplace drop based on condition : `df.drop(df[df.score < 50].index, inplace=True)`
 - drop row which contains nan : `df.dropna()`
 - sorting : `df.sort_values(by=”Age”, inplace=True, ascending=True)`
 - creation from list of tuples : `df = pd.DataFrame(list_of_tuples, columns =['Name', 'Age', 'Score'])`
 - read csv like : `pd.read_csv(path, sep=”\t”, skiprows=5, header=None)`
 - rename columns : `df.columns = [str(i) for I in range(100)]`
 - convert to csv : `df.to_csv(path, index=False, sep=”;”)`
 - add columns with values from dict : `for key, value in mon_dict.items():df[key] = value`
 - returns a groupby object, TCD-like : `df.groupby(by=[« age », “size”, “length”]).mean()`
 - add arbitrary numerical category to non-numerical data : `df[“data_num_cat”] = df[“data”].target.astype(“category”).cat.codes`
 - add mean value to all rows [see](https://stackoverflow.com/questions/10373660/converting-a-pandas-groupby-output-from-series-to-dataframe): `Pd.merge(df.groupby(by=”age”).mean().add_prefix(“mean_”).reset_index(), df)` 
 - drop based on condition : `df.drop(df[df.score < 50].index, inplace=True)`
 - loop over groups : `for name, sub_df in df.groupy(« age”): print(“for age ==”, name”, sub_df)`
 - loop over rows : `for index, row in df.iterrows(): print(row['c1'], row['c2'])`
 - drop last column : `df = df.iloc[:, :-1]`
 - add columns with index values : `df[« ImageIndex] = np.arange(len(df))`
 - merge with different columns name : `pd.merge(df1, df2, how='left', left_on=['a1', 'b'], right_on = ['a2','b'])`
 - change value based on value : `df.loc[df["age"]==10, "age"] = 12`
-           
 - turn row-series into df : 
 ```python
for idx, row in df.iterrows(): df_row = row.to_frame()
    df_row.columns = [“csv_name”]
    df_row = df_row.T
```
 - Convert columns dtype : To numeric : `df[["a", "b"]] = df[["a", "b"]].apply(pd.to_numeric)`
 - select numerical columns : `df.select_dtypes(include=np.number)` or `df._get_numeric_data()`
 - select names of numerical columns : `df.select_dtypes(include=np.number).columns.tolist()`
 - select categorical columns : `df.select_dtypes(include=['category'])`
 - select boolean columns : `df.select_dtypes(include=['bool']).columns.tolist()`  

 
# Duplicates
 - returns all duplicate rows (except first occurrence) : `duplicateRowsDF = dfObj[dfObj.duplicated()]`
 

# Creation

 - serie from list : `S = pd.Series(my_list)`
 - empty dataframe : `df = pd.DataFrame(columns=['A','B','C'])`
 - from numpy array : `pd.DataFrame(data_np_array, index=index_list, columns=[“A”, “B”, “C”])`
 - from dict : `df2 = pd.DataFrame({'A': 1.,'B':pd.Timestamp('20130102'),'C': pd.Series(1,index=list(range(4)), dtype='float32'),'E': pd.Categorical(["test", "train", "test", "train"]), 'F': 'foo'})`
 - from data and index list : `pd.Dataframe(data=data, index=row_labels)` 
 - enforce column order (where d has keys x, y , z) : `pd.DataFrame(d, index=[100, 200, 300], columns=['z', 'y', 'x'])` : 
 - from nested list : `pd.DataFrame([[1, 2, 3], [1, 2, 2], [1, 3, 3]], colums=['x', 'y', 'z'])` 
 - with list of dict : `pd.DataFrame([{"x":1, "y":2,'z':3},{"x":1, "y":2,'z':3}])`
 - from numpy array : `pd.DataFrame(arr, columns=["x", "y", "z"], copy=True)`
 - from file : `pd.read_csv('data.csv', index_col=0)`


# Introspect


## introspect Series


 - `s.describe()` : return descriptive statistics (min/max/count/mean/std/…)
 - `s.unique()` : list unique values in serie
 - `s.value_counts()` : histogram


## introspect Dataframe  

 - `df.info()`
 - `df.describe()` : return descriptive statistics (min/max/count/mean/std/…)
 - `df2.dtypes` : data types of cols
 - `df.ndim` 
 - `df.head()` : print head top of df
 - `df.tail()` : print tail end of df
 - `df.index`: show the index column (==sequence of row labels)
 - `df.columns` : show the columns name (sequence of column labels)
 - `df.size`
 - `df.mean()` : mean of cols
 - `df.shape` : number of row and cols
 - `df[“TCN”].unique()` : List different values
 - `df[“w”].nunique()` : number of unique values
 - `for col in df: print(f"{col:>30}", df[col].unique())` : list of unique values in all cols 
 - `for index, row in df.iterrows(): print(row['c1'], row['c2'])` : loop over rows
 - `df.values or df.to_numpy()` : get the raw data (without labels) (or` df.to_numpy(copy=True, dtype=float)`)
 
 
## iteration

- iteration over columns : `for col_label, col in df.iteritems(): print(col_label, col, sep='\n', end='\n\n')`
- iteration over columns : `for col_label, col in df.items(): print(col_label, col, sep='\n', end='\n\n')`
- iteration over rows : `for row in df.loc[:, ['name', 'city', 'total']].itertuples(): print(row)`


# Merge/concat 

Concat and merge are the main functions. Join and append are shortcuts.


## merge

Use merge when data is relevant for the merging 

 - Default merge : `how=”inner”` : Inner merge : merge columns and only keep rows that appear in both df (intersect columns names, keep rows where the values of these columns overlap)
 - By default, will use all columns name that overlap : `on=None`, equivalent to `on=[list of all columns names that are in both df]`
 - `How=”outer”` : keep all rows, adding `nan` where values are missing
 - `pd.merge(df1, df2, how="left")` : keep all rows of left df, and add data to rows that appear in right df (output has same length as left df)
 - Concatenate df col-wise (augment) : `pd.merge(left_df, right_df, on='A')` (defaults to inner merge)


## concatenate


Merge df without comparing data

 - Concatenate df row-wise (pile): `pd.concat([df1, df2])`, equivalent to axis=0
 - Concatenate df column-wise (augment) : `pdf.concat([df1, df2], axis=1)`
 - `ignore_index=False` by default will keep index from both df. `ignore_index=True` will create new index for output df
 - `join=”outer”` by default will keep all data and fill missing with nan.`join=’inner”` will only keep columns that appear in both df
  
## other tools for merging

 - Join : `on=None` by default will join index-wise
 - `df1.join(df2)` : augment column-wise
 - If some columns have same name, use suffix to explicitly precise which is from where :`df1.join(df2, lsuffix=”_x”)`
 - Append data : `df = df.append({"firstname": "John", "lastname":"Johny"}, ignore_index=True)` # careful, not in-place append
 

# Subselection


## subselection based on values

 - Select single cols : `df[“A”]`
 - Select rows : `df[0:3]`
 - Select multiple cols : `df.loc[:, ['A', 'B']]`
 - Select multiple cols and index : `df.loc['20130102':'20130104', ['A', 'B']]`
 - Select with multiple conditions : `df.loc[(df['A'] >= 0) & (df['B'] <= 10)`
 - Select with condition, only some columns : `df.loc[df['a'] > 10, ['a','c']]` (with parent’s!)
 - Select single value : `df.at[dates[0], 'A']` (equivalent to `df.loc[dates[0], 'A']`)
 - `df.loc[10]` : get row with label 10 (inclusive slicing)
 - `df.at[label_row, label_col]` : return single value
 - `df['age'][101]` : get 'age' value of row with index 101


## subselection based on index

 - Select rows by index : `df.iloc[3]`
 - Select rows and cols by index : `df.iloc[3:5, 0:2]`
 - Select single value based on index : `df.iat[1, 1]` (equivalent to `df.iloc[1, 1]`)
 - `df.iloc[10]` : get 10th row (exclusive closing slicing)
 - `df.at[label_row, label_col]` : return single value
 - Set value by position : df.iat[0, 1] = 0


## subselection boolean based on condition

 - Numerical value on all df: `df[df > 0]`
 - Numerical value on col : `df[df['A'] > 0]`
 - Select specific values : `df2[df2['E'].isin(['two', 'four'])]` (select rows where “E” col equals two or four)
 - `df[df['django-score'] >= 80]`
 - `df[(df['py-score'] >= 80) & (df['js-score'] >= 80)]`
 - `df['django-score'].where(cond=df['django-score'] >= 80, other=0.0)`




 
# Add/Delete/Modify

- dtypes : `df_ = df.astype(dtype={'age': np.int32, 'py-score': np.float32})`
- rows 
 - `df = df.append(pd.Series(data=['John', 'Boston', 34, 79], index=df.columns, name=17)`
 - `df = df.drop(labels=[17])` (use inplace inplace=True)
- cols
 - dict style : `df['js-score'] = np.array([71.0, 95.0, 88.0, 79.0, 91.0, 91.0, 80.0])`
 - `df['js-score']` = 0 #same value every rows
 - `df.insert(loc=4, column='django-score', value=np.array([86.0, 81.0, 78.0, 88.0, 74.0, 70.0, 81.0]))`
 - `del df["toto"]`
 - `df.pop('toto')`
 - `df = df.drop(labels='age', axis=1)`
 - `sub_df = df.loc[:, [“A”, “B”]]`
 - `df.iloc[:, 1:9])`
 - `df.drop(columns=['Length','Height'])`
 - `df = df.iloc[3:]` : remove rows
- index : 
 - `df.index += 1`
 - `df.index = range(1,len(df)+1)`
 - function to cols : `df.apply(np.cumsum)`
 - function to cols : `df.apply(lambda x: x.max() - x.min())`


# Sorting

 - `df.sort_values(by='js-score', ascending=False)`
 - `df.sort_values(by=['total', 'py-score'], ascending=[False, False])`
 - `df.sort_values(by=['total', 'py-score'], ascending=[False, False], inplace=True)`
 - `df.sort_index(axis=1, ascending=False)` : sort data by columns name
 - `df.sort_values(by='B')` : sort data by columns values

 
# Missing data

- exclude or include NaNs : `skipna=False`
- replace missing data with value : `df.fillna(value=0)`
- replace missing data with value of preceding row : `df.fillna(method='ffill')`
- replace missing data with value of next row : `df.fillna(method='bfill')`
- replace missing data with interpolation : `df.interpolate()`
- drop missing data row : `dropna()`


# Pivot table

```python
pd.pivot_table(data,
    values=None,         # values to summup: column to aggregate, optional 
    index=None,          # index : row-sorting : column, Grouper, array, or list of the previous
    columns=None,        # columns: col-sorting :column, Grouper, array, or list of the previous
    aggfunc='mean',      # aggfunc: function to use : function, list of functions, dict, default numpy.mean
    fill_value=None,     # fill_value: scalar, default None
    margins=False,       # margins: add totals: bool, default False
    dropna=True,         # dropna: bool, default True
    margins_name='All',  # margins_name: str, default ‘All’
    observed=False       # observed: bool, default False
)
```

 - display sum of fares row-sorted by sex, then class :
```python
pd.pivot_table(df, 
               values='fare',
               index=['sex', 'class'],
               aggfunc=np.sum)
```
 - display mean of fares by sex on rows and class on cols : 
```python
pd.pivot_table(
    df, 
    values='fare',
    index='sex',
    columns='class',
)
```
 - display sum of fares and mean of age row-sorted by sex then class :
```python
pd.pivot_table(
    df, 
    values=['fare', 'age'],
    index=['sex', 'class'],
    aggfunc={'fare': np.sum,
             'age': np.mean})
```
 - display mean of fares, and min/max/mean of age, row-sorted by who then class : 
```python
pd.pivot_table(
    df,
    values=['fare', 'age'],
    index=['who', 'class'],
    aggfunc={'fare': np.mean,
             'age': [min, max, np.mean]})
```
 
 To plot pivot table : 
 ```python
sns.heatmap(pt, annot=True, xticklabels=True, yticklabels=True)
sns.heatmap(pt.interpolate(method=”quadratic”), annot=True, xticklabels=True, yticklabels=True)
```
 
# Plotting

## basic plots

 - histogram a Serie : `boston_df['AGE'].plot.hist(bins=10)`
 - plot a df : `df.plot()`
 - `df.plot(x ='Unemployment_Rate', y='Stock_Index_Price', kind = 'scatter')` #line, bar
 - `ax = df.plot(x=”x”, y=”y1”, color=”blue”, kind=”scatter”); df.plot(x=”x”, y=”y2”, color=”blue”, kind=”scatter”)`
 - `df.boxplot(by ='day', column =['total_bill'])`
 - `df.boxplot(by ='day', column =['total_bill', 'discount'])`
 - `temp.plot().get_figure().savefig('temperatures.png')`
 - `df.loc[:, ['py-score', 'total']].plot.hist(bins=5, alpha=0.4)` : overlay histrograms
 - plot X Y with colored z : `plt.scatter("age", "weigh", c='country',data=df)`


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

# ressources : 
https://towardsdatascience.com/interactive-controls-for-jupyter-notebooks-f5c94829aee6




 
# see melt, unstack, explode
Df.melt()
Df.melt(“x”)


 