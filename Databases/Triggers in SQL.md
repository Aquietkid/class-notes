Triggers are a special kind of stored procedure which is executed by the DBMS automatically whenever a certain query is executed. Triggers are used to prevent unauthorized and accidental actions from destroying the database. They can not be executed by the user or the client application directly: they execute only when the specified actions are performed. 

The general syntax for __DDL triggers__ is: 
```SQL
CREATE TRIGGER <trigger_name>
ON [ALL SERVER | DATABASE]
WITH [trigger_option]
FOR <event_type(s)>
AS
BEGIN
<trigger_body>
END
```

The general syntax for __DML triggers__ is: 
```SQL
CREATE [ OR ALTER ] TRIGGER [ schema_name . ]trigger_name  

ON { table }  

[ WITH <dml_trigger_option> [ ,...n ] ] 

{ FOR | AFTER }  

{ [ INSERT ] [ , ] [ UPDATE ] [ , ] [ DELETE ] }  

AS BEGIN { sql_statement  [ ; ] [ ,...n ] } END

<dml_trigger_option> ::= 

    [ NATIVE_COMPILATION ] 

    [ SCHEMABINDING ] 

    [ EXECUTE AS Clause ]
```
# Types of Triggers
- Instead of: these triggers prevent the specified action from being performed. 
- After: these triggers execute when a specified action has been performed. 