> What makes one grouping of attributes into relations better than another? 

# Goodness of Database Design
Goodness of a database design is measured in two dimensions: 
1. __Logical/Conceptual Level__: how users interpret the schema and meanings of the attributes
2. __Implementation/Physical Storage Level__: how tuples in a base relation are stored and updated
# Design Methods
## Bottom-Up
Start by creating binary relations among attributes, and perform grouping to create the final schema. Not used practically because many binary relations appear. 
## Top-Down
Start with a logical grouping of attributes as they appear naturally, and then empirical decomposition to achieve the desired properties. 

---
Normalization alone does not guarantee a good database design. Relational schemas should exhibit the _lossless join_ property, and the _dependency preservation_ property. Lossless or nonadditive join prevents the generation of spurious tuples (tuples which represent invalid data); while dependency preservation requires that each functional dependency be represented in its own relation. 
# 1NF (First Normal Form) 
Previously, a table not in $1NF$ could still be a relation. The first normal form ($1NF$) is considered now to be part of the formal definition of a relation. $1NF$ removes [[Multivalued Attributes|multivalued attributes]], composite attributes, and combinations of these two, and suggests the use of _atomic_ and indivisible values for attributes. 
## Methods to Achieve 1NF
1. Split the relation into two relations based on the attribute which violates 1NF. This attribute is placed in another relation with the primary key of the initial relation, both of which combine to form the primary key of the new relation. 
2. Without splitting the relations, expand the primary key to include the attribute which violates $1NF$. However, this introduces redundancy. 
3. If the upper limit of the number of values an attribute can assume is known, the attribute is split into multiple attributes as many in number as the upper limit. However, this adds NULL values where multiple values do not exist, causes problems in joins, makes queries more complex, and implies spurious semantic ordering which was not intended. 
# 2NF (Second Normal Form)
> A relation schema $R$ is in $2NF$ if every nonprime attribute $A$ in $R$ is fully functionally dependent on the primary key of $R$.

To bring a relation in $2NF$, decompose the relation so as to remove [[Functional Dependencies#Partial Functional Dependency|partial dependencies]] 

- If the primary key contains a single attribute, the test need not be applied at all.
- Remove [[Functional Dependencies#Partial Functional Dependency|partial dependencies]]: keys which uniquely identify a part of a relation. 
- Very often, relations are made by the join of data of different entities. These relations are decomposed into separate relations. 
# 3NF 
> A relational schema $R$ is in $3NF$ if it satisfies $2NF$ and no nonprime attribute of $R$ is transitively dependent on the primary key.

- Though $2NF$ and $3NF$ target different properties, it is historically a convention to maintain the order $1NF \rightarrow 2NF \rightarrow 3NF \rightarrow BCNF$ since Boyce and Codd defined it in that order. 
- Remove [[Functional Dependencies#Transitive Functional Dependency|transitive dependencies]]: candidate keys determining attributes 
# BCNF (Boyce-Codd Normal Form)
> A relation schema $R$ is in BCNF if whenever a nontrivial functional dependency $X → A$ holds in $R$, then $X$ is a superkey of $R$.