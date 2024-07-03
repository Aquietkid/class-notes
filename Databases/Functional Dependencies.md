> A functional dependency, denoted by $X → Y$, between two sets of attributes $X$ and $Y$ that are subsets of $R$ specifies a constraint on the possible tuples that can form a relation state $r$ of $R$. The constraint is that, for any two tuples $t1$ and $t2$ in $r$ that have $t1[X] = t2[X]$, they must also have $t1[Y] = t2[Y]$.
# Full Functional Dependency
A functional dependency $X → Y$ is a full functional dependency if removal of any
attribute $A$ from $X$ means that the dependency does not hold anymore; that is, for
any attribute $A ε X$, $(X − {A})$ does not functionally determine $Y$.
# Partial Functional Dependency
A functional dependency $X → Y$ is a partial dependency if some attribute $A ε X$ can be removed from $X$ and the dependency still holds; that is, for some $A ε X$, $(X − {A}) → Y$.
# Transitive Functional Dependency
A functional dependency $X → Y$ in a relation schema $R$ is a transitive dependency if there exists a set of attributes $Z$ in $R$ that is neither a candidate key nor a subset of any key of $R$ and both $X → Z$ and $Z → Y$ hold.
# Anomalies in Database Design
Anomalies in database schema design prevent new records from being added, deleted, or modified as required. 
- Insertion anomalies prevent adding new records of one entity unless it is related to another entity, or the relating attribute is sett to null. Insertion anomalies might try to make the primary key NULL, which is not possible. 
- Deletion anomalies cause all the records of an entity to get deleted when we want to delete just one. 
- Update anomalies make the change in each record of an entity when change is required only in a few entities. 
# Classification of Dependencies

- Trivial Dependency: $$ L.H.S \supseteq R.H.S$$
- Partially non-Trivial Dependency: $$ L.H.S \subseteq R.H.S $$
- Completely non-Trivial: $$  L.H.S \cap R.H.S = \phi$$
---
