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