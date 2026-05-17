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

Increase system capacity by adding multiple servers behind a [load balancer](LoadBalancer.md).

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

[Database Replication Strategies](./DbReplication.md)

- Cold Standby
- Warm Standby
- Hot Standby
- Multi-Primary
- **Sharding**

---

# Cloud Solutions:

Cloud solutions ([Cloud Storage & Data Lakes](./CloudSolutions.md)) provide scalable and cost-effective storage and processing capabilities for large volumes of data across distributed systems.

---

# Database ACID Properties

[ACID Principles](./AcidProperties.md)

- Atomicity
- Consistency
- Isolation
- Durability

---

# Database CAP Theorem

[CAP Theorem](./CAPTheorem.md)

A distributed system can guarantee only two out of the following three properties at the same time:

- Consistency
- Availability
- Partition Tolerence
