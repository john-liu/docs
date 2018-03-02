class: center, middle

# CAP Theorem Introduction

John Liu

2018-03-02

---



# Who 

.left-column30[
.img[
![Eric Brewer](https://people.eecs.berkeley.edu/~brewer/Brewer-small.jpg)
]
]
.right-column70[
* Tenured profession of UC Berkeley
* Creator of usa.gov (with Bill Clinton)
* VP of Google Infrastructure
* CAP theorem
]

---

# What

It is impossible for a distributed computer system to simultaneously provide all three of the following guarantees:

* **Consistency**, 
  * every read receives the most recent write or an error
  * all nodes see the same data at the same time
* **Availability**, every request received by a non-failing node must result in a response
* **Partition tolerance**, the system continues to operate despite arbitrary partitioning due to network failures



---



# Partition Tolerance

* Partition **MAY** happen.
* The system should **continue** to operate.
* CA system, single host, ACID

---

# Availability

* Always respond if alive
* Dead node doesn't count

---

# Consistency

* Not the C in ACID

* distributed linearizability

* read & write, optimistic & pessimistic

  * Logical: read-read, read-write, read-your-write


  * replication-consistency: inconsistency-window & Eventually Consistency

* trade off durability, latency

* Strong Consistency, R + W > N

---

# What's more

* "2 of 3" tends to oversimplify
* Nuances matter a lot.
* More continuous than binary
  * A, 0~100
  * C, multiple levels
* Manage partitions
  * Detect partition
  * Limit operations
  * recovery
