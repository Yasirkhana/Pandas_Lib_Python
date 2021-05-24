```python
## Pandas Provide data sturcture to store data
```

# Series In Panda


```python
import pandas as pd
```


```python
s1 = pd.Series([1,2,3,4])      # Creating Series with List
s1                             # o,1,2,3 is key &&& 1,2,3,4 is value
```




    0    1
    1    2
    2    3
    3    4
    dtype: int64




```python
type(s1)
```




    pandas.core.series.Series




```python
s2 = pd.Series(([1,2,3,4]), index=(["a","b","c","d"]))   # We can also assign custom index
s2
```




    a    1
    b    2
    c    3
    d    4
    dtype: int64




```python
s3 =pd.Series({'a':1,'b':2,'c':3, 'd':4})      # Creating Series with Dictionary
s3
```




    a    1
    b    2
    c    3
    d    4
    dtype: int64




```python
type(s3)
```




    pandas.core.series.Series




```python
s3 =pd.Series({'a':1,'b':2,'c':3, 'd':4}, index =["w","a","y","b"])     # Repositioning Indexes

s3
```




    w    NaN
    a    1.0
    y    NaN
    b    2.0
    dtype: float64




```python
s2[2]  # Exract spacific value
```




    3




```python
s2[1:]   # Exract spacific range of value
```




    b    2
    c    3
    d    4
    dtype: int64




```python
s4 = pd.Series([1,2,3,4,5,6,7,8,9])
s4
```




    0    1
    1    2
    2    3
    3    4
    4    5
    5    6
    6    7
    7    8
    8    9
    dtype: int64




```python
s4+2                     # adding 2 in s4(Each element plus 2 hu jai ga)
```




    0     3
    1     4
    2     5
    3     6
    4     7
    5     8
    6     9
    7    10
    8    11
    dtype: int64



# DataFrame (Important)


```python
# Provide Rows and Columns just like excel Sheet
# 2d label data structure
```


```python
import pandas as pd
```


```python
es1 =pd.DataFrame({"Names":["Yasir","Bilal","Sunny"],"Ids":[100,244,155]})                              #Important 
```


```python
es1
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
      <th>Names</th>
      <th>Ids</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Yasir</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bilal</td>
      <td>244</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sunny</td>
      <td>155</td>
    </tr>
  </tbody>
</table>
</div>




```python
type(es1)
```




    pandas.core.frame.DataFrame




```python
y1 = pd.DataFrame({                                           # DO PRACITCE ALOT
    "Name":["Yasir","Bilal","Sunny"],
    "Department":["COICS","BBA","Eng"],
    "Sallary":[10000,50000,12341],
    "ProLang":["Python","None","None"]})
y1
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
      <th>Name</th>
      <th>Department</th>
      <th>Sallary</th>
      <th>ProLang</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Yasir</td>
      <td>COICS</td>
      <td>10000</td>
      <td>Python</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bilal</td>
      <td>BBA</td>
      <td>50000</td>
      <td>None</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sunny</td>
      <td>Eng</td>
      <td>12341</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
</div>




```python
#!     Formate for making datadrames
pd.DataFrame({ 
    "Name":[],
    "Ids":[],
    "Sono..":[]
})         
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
      <th>Name</th>
      <th>Ids</th>
      <th>Sono..</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>



# Methods Of DataFrames/


```python
# Function In DataFrames : 
# (i): head():  To see First 5 rows of DataFrame
# (ii): shape(): To find no.of rows/columns in a DataFrame
# (ii): describe(): General Info About DataFrame
# (iv): tail(): To see Last 5 rows of DataFrame
# (v): drop(): Use to Drop row or coumn (e.g={ y1.drop("Name",axis = 1)   })
# (vi): iloc[]
# (vii): loc[]
```


```python
# Method To Read CSV File :
# E.g:
#    iras = pd.read_csv("filename.csv")   

```


```python
y1.shape   # shape(): To find no.of rows/columns in a DataFrame

```




    (3, 4)




```python
y1.describe
```




    <bound method NDFrame.describe of     Name Department  Sallary ProLang
    0  Yasir      COICS    10000  Python
    1  Bilal        BBA    50000    None
    2  Sunny        Eng    12341    None>




```python
#  iloc[] : Use to extract data from DatFrame
```


```python
y1.iloc[0:1 , 0:1]      # Extacting 1st row and 1st col from y1
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
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Yasir</td>
    </tr>
  </tbody>
</table>
</div>




```python
y1.loc[0:2,"Department"]   # Extracting by name of calumn 
```




    0    COICS
    1      BBA
    2      Eng
    Name: Department, dtype: object



# Basic Function In Pandas

##### 1 . Mean()
##### 2 . Median()
##### 3 . Maximum()  => max()
##### 4 . Minimun()   => min()


```python
y1.min()
```




    Name          Bilal
    Department      BBA
    Sallary       10000
    ProLang        None
    dtype: object




```python
y1.max()
```




    Name           Yasir
    Department       Eng
    Sallary        50000
    ProLang       Python
    dtype: object




```python
def half(data):
    return data/2               # Custom Function to half something

y1[["Sallary"]].apply(half)       # Applying half funciton to half the sallaries
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
      <th>Sallary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5000.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>25000.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6170.5</td>
    </tr>
  </tbody>
</table>
</div>




```python
y1["Name"].value_counts()           # Count specific value occur
```




    Yasir    1
    Sunny    1
    Bilal    1
    Name: Name, dtype: int64




```python
y1.sort_values(by="Sallary")         # Sorting entries 
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
      <th>Name</th>
      <th>Department</th>
      <th>Sallary</th>
      <th>ProLang</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Yasir</td>
      <td>COICS</td>
      <td>10000</td>
      <td>Python</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sunny</td>
      <td>Eng</td>
      <td>12341</td>
      <td>None</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bilal</td>
      <td>BBA</td>
      <td>50000</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
</div>



### THE END 


```python

```
