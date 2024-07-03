# Schedule
> A schedule (or history) $S$ of $n$ transactions $T_1, T_2, … , T_n$ is an ordering of the
operations of the transactions.

# ACID Properties of Transactions
- **Atomicity**. A transaction is an atomic unit of processing; it should either be performed in its entirety or not performed at all.
- **Consistency preservation**. A transaction should be consistency preserving, meaning that if it is completely executed from beginning to end without interference from other transactions, it should take the database from one consistent state to another.
- **Isolation**. A transaction should appear as though it is being executed in isolation from other transactions, even though many transactions are executing concurrently. That is, the execution of a transaction should not be interfered with by any other transactions executing concurrently. 
- **Durability or permanency**. The changes applied to the database by a committed transaction must persist in the database. These changes must not be lost because of any failure.
# Conflict in Schedules
Two operations in a schedule are said to conflict if they satisfy all three of the following conditions: 
1. they belong to different transactions 
2) they access the same item X
3) at least one of the operations is a write_item(X). 
# Complete Schedules
A schedule $S$ of $n$ transactions $T_1, T_2, … , T_n$ is said to be a complete schedule if the following conditions hold:
1. The operations in $S$ are exactly those operations in $T_1, T_2, … , T_n$, including a commit or abort operation as the last operation for each transaction in the schedule.
2. For any pair of operations from the same transaction $T_i$, their relative order
of appearance in $S$ is the same as their order of appearance in $T_i$.
3. For any two conflicting operations, one of the two must occur before the
other in the schedule.
## Cascading Rollback
No committed transaction can be rolled back so as to preserve the durability. However, if a transaction $T_1$ reads an item from another transaction $T_2$, then $T_1$ commits, but $T_2$ is rolled back due to some failure, $T_1$ will also be rolled back through a __cascade rollback__. 
# Serial Schedule
> A schedule S is serial if, for every transaction T participating in the schedule, all the operations of T are executed consecutively in the schedule; otherwise, the schedule is called nonserial.

Serial schedules lock the CPU until a transaction completes. This causes long wait times for other processes, making serial schedules unacceptable. However, if we could use non-serial schedules equivalent to the serial schedule practically. 
__Serializable Schedule__
A schedule $S$ of $n$ transactions is serializable if it is equivalent to some serial schedule of the same $n$ transactions.
## Equivalence of Schedules
### Result Equivalence
Two schedules are __result equivalent__ if they produce the same results. However, this is a crude way of defining equivalence, since the two schedules may accidentally be giving the right answer. 
### Conflict Equivalence
Two schedules are __conflict equivalent__ if the relative order of any two conflicting operations is the same in both schedules. 
## Serializable Schedule
A schedule is serializable if 