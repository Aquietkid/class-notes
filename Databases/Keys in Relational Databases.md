# Keys
- __Primary key__: uniquely identifies a row, can not be null.
- __Secondary key__: candidate keys which are not made the primary key
- __Candidate key__: any key that could be made a primary key because it uniquely identifies a record. 
	- If a relation schema has more than one key, each is called a candidate key. One of the candidate keys is arbitrarily designated to be the primary key, and the others are called secondary keys.
- __Unique key__: uniquely identifies a row, but allows a single null value. More than one null value would violate uniqueness.
- __Foreign Keys__: a primary key in another relation used to define the relation with an entity of another relation
- __Superkey__: any set of attributes of a relation which uniquely identify records in the relation is the superkey. Superkeys have a key as their part. 
	- A superkey of a relation schema $R = {A1, A2, … , An}$ is a set of attributes $S ⊆ R$ with the property that no two tuples $t1$ and $t2$ in any legal relation state $r$ of $R$ will have $t1[S] = t2[S]$. 
	- A key $K$ is a superkey with the additional property that removal of any attribute from $K$ will cause $K$ not to be a superkey anymore.
# Finding Candidate Keys
Determine prime and non-prime attributes. All prime attributes must be part of any key. Find attribute closures for the prime attributes, then keep adding more attributes to the key, while making sure that it is not a superkey. All keys resulting with a closure same as all the attributes of the relation is a candidate key. 
# Prime and Non-Prime Attributes
## Prime Attributes
Prime attributes are member of a candidate key in a relation. 
## Non-Prime Attributes
Non-prime attributes are not a member of any candidate key. 
# [[Database Constraints]]
