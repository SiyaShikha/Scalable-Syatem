# Acid Properties

- Atomicity
- Consistency
- Isolation
- Durability

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
