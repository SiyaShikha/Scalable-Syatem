# Database Replication Strategies

## Cold Standby

The backup system remains offline until the primary system fails.

Problem:

- Data after the last backup may be lost

---

## Warm Standby

A continuously running replica exists in another location.

- Faster recovery than cold standby
- Some replication delay may exist

---

## Hot Standby

Real-time replication between primary and standby databases.

- Minimal data loss
- High availability

---

## Multi-Primary

Application writes directly to multiple database servers.

Benefits:

- High availability
- Better write scalability

Challenges:

- Conflict resolution
- Increased complexity

---

# Sharding

Splits a large database into smaller independent databases called _shards_.

Benefits:

- Improves scalability
- Reduces load on a single database
- Each shard can have its own backup and replication

Example:

- Users 1–1M → Shard A
- Users 1M–2M → Shard B
