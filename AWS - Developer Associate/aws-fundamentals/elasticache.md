# ElastiCache

  - Is to get managed Redis or Memcached
  - Cache are in-memory databases with really high performance, low latency
  - Helps reduce load off of databases for read intensive workloads
  - Helps make your application stateless
  - AWS takes care of OS maintenance / patching, optimizations, setup, configuration, 
  monitoring, failure recovery and backups
  - Using ElastiCache involves heavy application code changes

### Solution Architecture

  - DB cache
    - Application queries ElastiCache, if not available, get from RDS and store in ElastiCache
    - Helps relieve load in RDS
    - Cache must have an invalidation strategy to make sure only the most current data is used in there

  - User Session Store
    - User logs into any of the application
    - The application writes the session data into ElastiCache
    - The user hits another instance of our application
    - The instance retrivies the data and the user is already logged in

  - Redis (replication)
    - Multi AZ with Auto-failover
    - Read Replicas to scale reads and have high availability
    - Data durability using AOF persistence
    - Backup and restore features

  - Memcached (sharding)
    - Multi-node for partitioning of data (sharing)
    - No high availability (replication)
    - Non persistent
    - No backup and restore
    - Multi-threaded architecture

### Caching Implementation 

  - https://aws.amazon.com/caching/implementation/considerations