Transactions are a powerful abstraction that databases provide for a group of operations.

They simplify the programming model at application level, giving many other benefits.

What is a transaction and what the acronym ACID means: {1/9} ↓

A transaction abstracts all the operations in a group into a single atomic operation.

Either all the operations in the group or none of them complete successfully. 

Let's consider as an example a payment from a bank account to another.

{2/9}

The payment needs 2 operations:

- withdraw money from an account
- deposit money in another account

The payment succeeds only if the 2 operations execute atomically and complete.

Encapsulating the 2 operations in a transaction is the way to achieve this.

{3/9}

Implementing transactions in a single relational database is quite straightforward.

But it's challenging having transactions where multiple distributed data stores are involved.

This is often the case for microservices where each service has its own database.

{4/9}

In a single traditional relational database, transactions guarantee ACID properties.

ACID is an acronym for Atomicity, Consistency, Isolation and Durability.

This is what each part of the acronym actually means.

{5/9}

1. Atomicity

It guarantees that all the operations in a transaction or none of them complete successfully.

Partial failures are not possible for whatever reason.

If one of the operations fails all the changes made need to be undone.

{6/9}

2. Consistency

It guarantee that any application level state is invariant after a transaction execute.

It's responsibility of the application to define consistent transactions.

In the payment example, the invariant state is the sum of money in the 2 bank accounts.

{7/9}

3. Isolation

It guarantees that the concurrent execution of transaction doesn't cause race conditions.

So to each transaction T it appears that other transactions are executed either before T or after T.

{8/9}

4. Durability

It guarantees that every change caused by a transaction persists in the database.

Data persistency shall be ensured even in case of system failures.

{9/9}
