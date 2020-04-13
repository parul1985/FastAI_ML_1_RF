## Lecture-1 

**Curse of dimensionality**


**No free lunch theorem**
In real-word there are techniques better for a lot of datasets. 

**Random Forest**
- Regressor: predict continuous variables
- Classifier: predict categorical variables


- ??: gives source code
- ?:  gives docs


#### Reading csv file:

```
df_raw = pd.read_csv(f'{PATH}Train.csv', low_memory=False, parse_dates=["saledate"])
```

- parse_dates:  converted “saledate” into datetime64[ns] format 

#### add_datepart

- add_datepart converts a column of df from a datetime64 to many columns containing
the information from the date. This applies changes inplace.

- Without expanding your date-time into these additional fields, you can't capture any trend/cyclical behavior as a function of time at any of these granularities.

```
add_datepart(df, fldnames, drop=True, time=False, errors='raise')
```

```
- df: A pandas data frame. df gain several new columns.

- fldname: A string or list of strings that is the name of the date column you wish to expand. 
- If it is not a datetime64 series, it will be converted to one with pd.to_datetime.

- drop: If true then the original date column will be removed.
time: 

- If true time features: Hour, Minute, Second will be added.
```

The categorical variables will be of the format: 

```
AYear AMonth AWeek ADay ADayofweek ADayofyear AIs_month_end AIs_month_start AIs_quarter_end AIs_quarter_start AIs_year_end AIs_year_start AElapsed
```


**pd.to_feather**

**proc_df**

- proc_df takes a data frame df and splits off the response variable, and
changes the df into an entirely numeric dataframe. 

- For each column of df 
which is not in skip_flds nor in ignore_flds, na values are replaced by the
median value of the column.

- converting everything to numerical as RF requires all the variables to have numerical data type. Otherwise you get the error

```
ValueError: could not convert string to float: 'Low'
```

**n_jobs**

```
m = RandomForestRegressor(n_jobs=-1)
```

**OOB-score**


**set_rf_samples**

- how is this different from boot-strapping in sklearn


**reset_rf_samples()**

sales_time.dt...


- train_cats: same mapping between of categorical variable between train and validation datasets

- order does not make much difference

- For RF its more like I am in Medium rather than low or high 
- How will order help in RF
- -1 for na
- diff between set_categories vs get_dummies


Date-Time: depending on what you are doing
- mont, date, year
- day of week
- week of month
- Quarter 
- Weekend
- Holiday 
- was it raining etc.. (dpepending on what you are doing)


**Python attribute**
getattr()


