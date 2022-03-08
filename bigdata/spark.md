## Spark
Spark application consists of a driver program that runs the user's main function and executes various parallel operations on a cluster.

### Abstractions
  1. RDD - collection of elements partitioned across the nodes of the cluster that can be operated in parallel.
  2. Shared Variables - shared between tasks.
      - Broadcast Variables - cache a value in memory on all nodes.
      - Accumulators - variables that are only added to, such as counters and sums.


### References
- https://spark.apache.org/docs/latest/rdd-programming-guide.html
- https://spark.apache.org/docs/latest/sql-programming-guide.html
