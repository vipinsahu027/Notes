##### DDL and StructType()


printSchema is used to see the schema of DF

![[Print Schema.png|400x300]]



###### DDL SCHEMA
this method can be used by using data defination
```python
my_ddl_schema = '''
                    Item_Identifier STRING,
                    Item_Weight STRING,
                    Item_Fat_Content STRING,
                    Item_Visibility DOUBLE,
                    Item_Type STRING,
                    Item_MRP DOUBLE,
                    Outlet_Identifier STRING,
                    Outlet_Establishment_Year INT,
                    Outlet_Size STRING,
                    Outlet_Location_Type STRING,
                    Outlet_Type STRING,
                    Item_Outlet_Sales DOUBLE
                '''
df = spark.read.format('csv')\
    .schema(my_ddl_schema)\
        .option('header',True)\
            .load('/FileStore/tables/BigMart_Sales.csv')
```

Or by using StructType()
```python
my_strct_schema = StructType([
							  StructField('Item_Identifier',StringType(),True),
							  StructField('Item_Weight',StringType(),True),
							  StructField('Item_Fat_Content',StringType(),True),
							  StructField('Item_Visibility',StringType(),True),
							  StructField('Item_MRP',StringType(),True),
							  StructField('Outlet_Identifier',StringType(),True),
							  StructField('Outlet_Establishment_Year',StringType(),True),
							  StructField('Outlet_Size',StringType(),True),
							  StructField('Outlet_Location_Type',StringType(),True),
							  StructField('Outlet_Type',StringType(),True),
							  StructField('Item_Outlet_Sales',StringType(),True)
])

df = spark.read.format('csv')\
            .schema(my_strct_schema)\
            .option('header',True)\
            .load('/FileStore/tables/BigMart_Sales.csv')
```

