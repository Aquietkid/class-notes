# Creating schemas
Schemas allow different users to have different authentications. It is not necessary to specify a schema.
```sql
create schema schemaName
```
# Deleting Databases
```SQL
DROP DATABASE [db_name];
```
# Creating Tables
- Adding square brackets around the name of an attribute allows it to have spaces in between, e.g. `[Column Name]`. 
# Deleting Tables
```SQL
DROP TABLE [table_name];
```
# Retrieving Data from Relations
```SQL
SELECT {TOP} {DISTINCT} <attribute_list>
FROM <table_list>
JOIN <relation> ON <join_conditions>
WHERE <conditions_list>
GROUP BY <group_attributes>
HAVING <agg_fucntion_list>
ORDER BY <order_attributes> { ASC | DESC }
```
# [[Keys in Relational Databases]]

# Comments

```sql
-- this is an SQL comment
```

# Constraints

Naming a constraint is always a good practice. If not named, the constraint will have a random alphanumeric identifier assigned to it which can be hard to remember.

```sql
constraint constraint_name constraint_type (attribute)
```

## Types of Constraints

- `PRIMARY KEY`
- `UNIQUE`
- `CHECK`
    - `CHECK` (Price > 0 and Price < 1000)
    - Boolean operators `and`, `or`, and `not` can be used.
- `DEFALUT`: assign default values when no value is provided.

# [[SQL Built-in Functions]]
Different functions are present. PART OF SQL OR COMPILER????????
Drag and drop, or write in queries.
# Indexes
Allow faster searching. It is a good practice to index that which is accessed often, but indexing everything would rather take too much space and work counter-intuitively. Indexes involve B-trees (kinda binary trees). 
# Alterations in Tables
Changes can be made by dropping a table and re-creating it. However, dropping would delete all data. Hence we choose to `alter` tables.
- `ADD`
- `DROP`
- `RENAME`
# Domain
Domains are kind of custom data-types which can be used for multiple attributes at the same time. This acts like a variable for a data-type. The variable can be used in different places. Domains essentially allow reuse.
# Standard Comparison Operators

| Operator | Function                 |
| -------- | ------------------------ |
| =        | Equals                   |
| != OR <> | Not equal                |
| <        | Lesser than              |
| >        | Greater than             |
| <=       | Lesser than or equal to  |
| >=       | Greater than or equal to |

# `IS NULL` vs. `= NULL`
`IS NULL` vs. `= NULL`: SQL treats the NULL keyword as a string in the `=` version. In the `IS NULL` version, it is an explicit command with no such confusions. If any value is set to NULL manually, it might be read by the `=` version. 
# Subqueries
Subqueries are queries nested within queries. This allows for a more readable, structured, and modular method of retrieving data. 

## Uses of Subqueries
1. When a selection, updation, or deletion is to performed based on conditions which relate a tuple or a set of tuples to other tuples. 
## Operators
- `IN`: Checks whether a value is found in a list specified. 
- `NOT IN`: opposite of `IN`
- `ANY`: Checks whether the comparison is true for any of the values which are selected by the subquery. Returns a Boolean value. 
- `ALL`: Checks whether the comparison is true for all of the values which are selected by the subquery. Returns a Boolean value. 
## Correlated Nested Queries
A correlated nested query executes the inner query for each row processed by the outer query. This is much like a for loop. (for each row of outer query, execute inner query). These queries are used primarily when the result would vary with the tuple selected by the parent query. 
# Joins
## Anti-Joins
Anti-joins return all the rows in the primary table, for which no record exists in the secondary table. Which table is primary and which is secondary is determined by whether the anti-join is left or right. 
### Where to put the `IS NULL`? 
- Putting the `IS NULL` inside the `ON` clause returns unexpected results.
- Putting the `IS NULL` in the `WHERE` clause after the `ON` clause works as expected. 
Why is it so? Perhaps it is so because when multiple statements are part of the `ON` clause, it _joins_ the table multiple times for each condition. However, when the same thing is specified in a `WHERE` clause, it _filters_ the results based on the condition(s). 
