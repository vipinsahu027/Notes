```python
#Read Json File
df_json = spark.read.format('json')\
    .option('header',True)\
        .option('inferSchema',True)\
            .option('multiLine',False)\
                .load('/FileStore/tables/drivers.json')
```

```python
#Read CSV file
df = spark.read.format('csv')\
    .option('inferSchema',True)\
        .option('header',True)\
            .load('/FileStore/tables/BigMart_Sales.csv')
```

