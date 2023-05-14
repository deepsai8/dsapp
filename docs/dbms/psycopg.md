### Psycopg2

It is a package that can be used to integrate PostgreSQL with Jupyter Lab/Notebook





```python
l1 = [1, 2, 3, 4]
```


```python
l1.pop()
l1
```




    [1, 2]



<table border="1" class="dataframe">\n  <thead>\n    <tr style="text-align: right;">\n      <th></th>\n      <th>IndexType</th>\n      <th>Scan</th>\n      <th>EqualitySearch</th>\n      <th>RangeSearch</th>\n      <th>Insert</th>\n      <th>Delete</th>\n    </tr>\n  </thead>\n  <tbody>\n    <tr>\n      <th>0</th>\n      <td>no_index</td>\n      <td>BD</td>\n      <td>0.5BD</td>\n      <td>BD</td>\n      <td>2D</td>\n      <td>Search + D</td>\n    </tr>\n    <tr>\n      <th>1</th>\n      <td>hash</td>\n      <td>BD(R + 0.125) + 2BRC</td>\n      <td>2D</td>\n      <td>BD</td>\n      <td>4D</td>\n      <td>Search + 2D</td>\n    </tr>\n    <tr>\n      <th>2</th>\n      <td>btree</td>\n      <td>1.5BD</td>\n      <td>D$\\log_F$(1.5B)</td>\n      <td>D$\\log_F$(1.5B) + $log_2$(R) * C</td>\n      <td>Search + D</td>\n      <td>Search + D</td>\n    </tr>\n  </tbody>\n</table>


```python
import pandas as pd
```


```python
d = {'IndexType':['no_index', 'hash', 'btree'],
    'Scan':['BD', 'BD(R + 0.125) + 2BRC', '1.5BD'],
     'EqualitySearch': ['0.5BD', '2D', r'D$\log_F$(1.5B)'],
     'RangeSearch': ['BD', 'BD', r'D$\log_F$(1.5B) + $log_2$(R) * C'],
     'Insert': ['2D', '4D', 'Search + D'],
     'Delete': ['Search + D', 'Search + 2D', 'Search + D']
    }
```


```python
pd.DataFrame(d).to_html()
```




    '<table border="1" class="dataframe">\n  <thead>\n    <tr style="text-align: right;">\n      <th></th>\n      <th>IndexType</th>\n      <th>Scan</th>\n      <th>EqualitySearch</th>\n      <th>RangeSearch</th>\n      <th>Insert</th>\n      <th>Delete</th>\n    </tr>\n  </thead>\n  <tbody>\n    <tr>\n      <th>0</th>\n      <td>no_index</td>\n      <td>BD</td>\n      <td>0.5BD</td>\n      <td>BD</td>\n      <td>2D</td>\n      <td>Search + D</td>\n    </tr>\n    <tr>\n      <th>1</th>\n      <td>hash</td>\n      <td>BD(R + 0.125) + 2BRC</td>\n      <td>2D</td>\n      <td>BD</td>\n      <td>4D</td>\n      <td>Search + 2D</td>\n    </tr>\n    <tr>\n      <th>2</th>\n      <td>btree</td>\n      <td>1.5BD</td>\n      <td>D$\\log_F$(1.5B)</td>\n      <td>D$\\log_F$(1.5B) + $log_2$(R) * C</td>\n      <td>Search + D</td>\n      <td>Search + D</td>\n    </tr>\n  </tbody>\n</table>'




```python
d = {'eid':[1, 2, 3],'name':['Jackson', 'Jonathan', 'Nabi'], 'title':['Director', 'Professor', 'Engineer'], 'ssn':[None, None, None]}
df = pd.DataFrame(d)
df.to_csv('employees_2.csv', index = False)
```


```python
! pwd
```

    /Users/deepaksingh/Desktop/MSDS/RDBMS



```python
! conda env list
```

    # conda environments:
    #
    base                  *  /Users/deepaksingh/opt/anaconda3
    discom                   /Users/deepaksingh/opt/anaconda3/envs/discom
    env-cassandra            /Users/deepaksingh/opt/anaconda3/envs/env-cassandra
    env-obb                  /Users/deepaksingh/opt/anaconda3/envs/env-obb
    env-tensors              /Users/deepaksingh/opt/anaconda3/envs/env-tensors
    



```python
df = pd.read_csv('Iowa_Fleet_Summary_By_Year__County_And_Vehicle_Type.csv')
df.head()
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
      <th>Year</th>
      <th>Year Ending</th>
      <th>County Name</th>
      <th>County FIP</th>
      <th>Feature ID</th>
      <th>Motor Vehicle</th>
      <th>Vehicle Category</th>
      <th>Vehicle Type</th>
      <th>Tonnage</th>
      <th>Registrations</th>
      <th>Annual Fee</th>
      <th>Primary County Lat</th>
      <th>Primary County Long</th>
      <th>Primary County Coordinates</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2005</td>
      <td>12/31/2005</td>
      <td>No County</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Yes</td>
      <td>Automobile</td>
      <td>Automobile</td>
      <td>NaN</td>
      <td>3711</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2006</td>
      <td>12/31/2006</td>
      <td>No County</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Yes</td>
      <td>Motor Home</td>
      <td>Motor Home - A</td>
      <td>NaN</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2008</td>
      <td>12/31/2008</td>
      <td>No County</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Yes</td>
      <td>Automobile</td>
      <td>Automobile</td>
      <td>NaN</td>
      <td>14</td>
      <td>1021.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2008</td>
      <td>12/31/2008</td>
      <td>Ida</td>
      <td>19093.0</td>
      <td>465235.0</td>
      <td>Yes</td>
      <td>Bus</td>
      <td>Bus</td>
      <td>NaN</td>
      <td>5</td>
      <td>680.0</td>
      <td>42.386875</td>
      <td>-95.513496</td>
      <td>POINT (-95.5134962 42.3868747)</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011</td>
      <td>12/31/2011</td>
      <td>Jasper</td>
      <td>19099.0</td>
      <td>465238.0</td>
      <td>Yes</td>
      <td>Moped</td>
      <td>Moped</td>
      <td>NaN</td>
      <td>198</td>
      <td>1386.0</td>
      <td>41.686039</td>
      <td>-93.053765</td>
      <td>POINT (-93.053765 41.6860394)</td>
    </tr>
  </tbody>
</table>
</div>




```python
import psycopg2 as pg
```


```python
host = 'localhost'
port = 5432
database = 'msds691'
user = 'postgres'
password = 'postgres'
```


```python
conn = pg.connect(host = host, port = port, database = database, user = user, password = password)
```


```python
cur = conn.cursor()
```


```python
cur.execute("select * from employees2")
cur.fetchall()
```




    [(1, 'Jackson', 'Director', None),
     (2, 'Jonathan', 'Professor', None),
     (3, 'Nabi', 'Engineer', None)]




```python
cur.execute("select department_id from departments;")
data = cur.fetchall()
did_list = []
for i in data:
    did_list.append(i[0])
did_list
```




    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]




```python

```


```python

```


```python

```


```python
conn
```




    <connection object at 0x137a48c10; dsn: 'user=postgres password=xxx dbname=msds691 host=localhost port=5432', closed: 0>




```python
cur.close()
conn.close()
```


```python

```
