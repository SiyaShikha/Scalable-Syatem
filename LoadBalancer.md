# Load Balancer Strategies

## Round Robin

Requests are distributed sequentially across servers.

Example:

- Request 1 → Server A
- Request 2 → Server B
- Request 3 → Server C

---

## Partitioning

Requests are routed based on a specific rule.

Example:

- Users A–M → Server 1
- Users N–Z → Server 2
