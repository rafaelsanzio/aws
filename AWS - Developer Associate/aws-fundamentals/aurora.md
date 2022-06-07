# Amazon Aurora

  - Is a proprietary technology from AWS (not open sourced)
  - PostegreSQL and MySQL are both supported as Aurora DB 
  (that means your drivers will work as if Aurora was a Postgres or MySQL database)
  - Is "AWS Cloud optimized" and claims 5x performance improvement over MySQL on RDS, 
  over 3x the performance of Postgres on RDS
  - Storage automatically grows in increments of 10GB, up to 128TB
  - Can have 15 replicas while MySQL has 5, and the replication process is faster (sub 10ms replica lag)
  - Failover in Aurora is instantaneous. It's HA native
  - Costs more tha RDS (20% more), but is more efficient

### High Availability and Read Scaling

  - 6 copies of you data across 3 AZ
    - 4 copies out of 6 needed for writes
    - 3 copies out of 6 need for reads
    - Self healing with peer-to-peer replication
    - Storage is striped across 100s of volumes
  
  - One Aurora instance takes writes (master)
  - Automated failover for master in less than 30 seconds
  - Master + up to 15 Aurora read replicas serve reads
  - Support for Cross Region Replication

  - Features
    - Automatic fail-over
    - Backup and recovery
    - Isolation and security
    - Industry compliance
    - Push-button scaling
    - Automated Patching with zero downtime
    - Advanced monitoring
    - Routine Maintenance
    - Backtrack: restore data at any point of time without using backups

  - Security
    - Similar to RDS because uses the same engines
    - Encryption ar rest using KMS
    - Automated backups, snapshots and replicas are also encrypted
    - Encryption in flight using SSL (same process as MySQL and Postgres)
    - Possibility to authenticate using IAM token (same method as RDS)
    - You are responsible for protecting the instance with security groups
    - You can't SSH

