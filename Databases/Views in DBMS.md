Views are logical tables based on physical tables. Data inside views can be updated and deleted, and views can be truncated. 
# SQL
```SQL
CREATE VIEW view_name AS (
	--SELECT ...
	-- FROM ...
	-- JOIN ...
)
```
# Simple View
Select tuples from a single physical table. 
# Complex View
Select tuples from multiple physical tables using joins. 
# Materialized View
A view that is stored on the disk for further processing. 