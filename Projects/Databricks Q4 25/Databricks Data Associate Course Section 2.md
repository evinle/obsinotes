## Delta Lake
	- Open source storage framework
	- Fixes data lakes inconsistencies issues
	- Not a data warehouse
Stored in parquet format and transaction log
Transaction logs
	- Ordered records of every transaction
Writer and Reader process
Writer don't update old files, instead makes a copy and update the transaction logs
Parquet + JSON

## Catalog
``` sql
USE CATALOG hive_metastore
```
like sql
```sql
DESCRIBE DETAIL ...
```
parquet files are immutable?
```sql
DESCRIBE HSITORY employees
```
there are also checksums

## Time Travel

```sql
-- can also SELECT
RESTORE TABLE ... TO TIMESTAMP AS OF "..."
-- or
VERSION AS OF <number>
@v<number>
```

## Compacting
```sql
OPTIMIZE <table name> ZORDER BY <column name>
```
z order indexing?

## Vacuum
```sql 
VACUUM <table name> [retention period]
```
no time travel after
\_delta_log files inside of warehouse 
`dbfs:/user/hive/warehouse/employees/_delta_log/`

So compared to Snowflake, Databricks seems a lot more versatile and open. It does require more setup and expertise, but you can really customize your experience, which is great. Snowflake seems like they're taking the "Apple" approach to things where it's a very locked down, but optimized user experience, especially for BI analytics, and general SQL. They also store data in a proprietary format in the underlying COS, which needs to be ingested by snowflake before being read


### Data file layout
Data File Layout

The **organization and storage structure** of the underlying data files
that make up a **Delta table.**

Optimizing layout **helps** leveraging **data-skipping algorithms**

Optimization techniques:
Partitioning
Z-Order Indexing
Liquid Clustering

ûdemy