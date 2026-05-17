# Scalable Systems

## Scaling Approaches

### Vertical Scaling

Increase the capacity of a single server by adding more CPU, RAM, or storage.

- Simple to implement
- Limited by hardware capacity
- Expensive at scale
- Creates a single point of failure

Example:

- Upgrading a server from 8 GB RAM to 64 GB RAM

---

### Horizontal Scaling

Increase system capacity by adding multiple servers behind a load balancer.

- Better fault tolerance
- Easier to scale
- Requires stateless web servers

Example:

- Multiple application servers behind a load balancer

---

## Problem in Horizontal Scaling: Web Servers Must Be Stateless

In horizontally scaled systems, servers should not store user session data locally.

Why?

- Any request can go to any server
- Improves scalability and reliability

Common Solutions:

- Redis
- Distributed cache
- JWT tokens

---

## Load Balancer Strategies

### Round Robin

Requests are distributed sequentially across servers.

Example:

- Request 1 → Server A
- Request 2 → Server B
- Request 3 → Server C

---

### Partitioning

Requests are routed based on a specific rule.

Example:

- Users A–M → Server 1
- Users N–Z → Server 2

---

## Serverless Services

Cloud-managed services where infrastructure management is handled automatically.

Examples:

- AWS Lambda
- AWS Kinesis
- AWS Athena

Benefits:

- Auto scaling
- Pay-per-use
- Reduced operational overhead

---

# Database Scaling & Availability

## Database Single Point of Failure

Using only one database server is risky because if it fails, the entire application may become unavailable.

---

## Database Replication Strategies

### Cold Standby

The backup system remains offline until the primary system fails.

Problem:

- Data after the last backup may be lost

---

### Warm Standby

A continuously running replica exists in another location.

- Faster recovery than cold standby
- Some replication delay may exist

---

### Hot Standby

Real-time replication between primary and standby databases.

- Minimal data loss
- High availability

---

### Multi-Primary

Application writes directly to multiple database servers.

Benefits:

- High availability
- Better write scalability

Challenges:

- Conflict resolution
- Increased complexity

---

## Sharding

Splits a large database into smaller independent databases called _shards_.

Benefits:

- Improves scalability
- Reduces load on a single database
- Each shard can have its own backup and replication

Example:

- Users 1–1M → Shard A
- Users 1M–2M → Shard B

---

# Cloud Solutions: Cloud Storage & Data Lakes

A Data Lake stores massive amounts of structured and unstructured data.

Common Solutions:

- AWS S3
- Azure Data Lake Storage
- Google Cloud Storage

Use Cases:

- Analytics
- Big data processing
- Machine learning

---

# ACID Properties

## Atomicity

Either the entire transaction succeeds or the entire transaction fails.

Example:

- Money deducted from one account must also be added to another account.

---

## Consistency

Database rules and constraints must always remain valid.

- All database rules are enforced, or the entire transaction is rolled back

Example:

- No invalid foreign key references

---

## Isolation

Transactions running simultaneously should not interfere with each other.

Example:

- One transaction should not read incomplete data from another transaction

---

## Durability

Once committed, data remains saved even after crashes or power failures.

---

# CAP Theorem

A distributed system can guarantee only two out of the following three properties at the same time:

## Consistency

Do I get back what I just wrote immediately?

- Every read receives the latest written data

---

## Availability

Can the system continue working even if some nodes fail?

- The system continues to respond even if some nodes are down

---

## Partition Tolerance

Can the system continue operating despite network failures?

- The system continues operating even if communication between nodes breaks

---

## Practical Insight

In distributed systems, **Partition Tolerance** is usually mandatory.  
Therefore, systems often choose between:

- **CP Systems** → Prioritize Consistency
- **AP Systems** → Prioritize Availability
