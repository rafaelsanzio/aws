# Relational Database Service (RDS)

- It is a managed DB service for DB use SQl as a query language
- It allows you to create databases in the cloud that are managed by AWS
	- Postgres
	- MySQL
	- MariaDB
	- Oracle
	- Microsoft SQL Server
	- Aurora (AWS database)

- RDS x deploying DB on EC2
	- Automated provisioning, OS patching
	- Continuous backups and restore to specific timestamp
	- Monitorting dashboards
	- Read replicas for improved read performance
	- Multi AZ setup for Disaster Recovery (DR)
	- Maintenance windows for upgrades
	- Scaling capability (vertical and horizontal)
	- Storage backed by EBS (gp2 or iol)

	- Cannot SSH into your instances

### RDS Backups

- Backups are automatically enabled in RDS
- Daily full backup of the database (during the maintenance window)
- Transaction logs are backed-up by RDS every 5 minutes

- Snapshots
	- Manually triggered by the user
	- Retention of backup for as long as you want

### RDS - Storage Auto Scaling

- Helps you increase storage on your RDS DB instance dynamically
- When RDS detects you are running out of free db storage, it scales automatically
- Avoid manually scaling your db storage
- Have to set Maximum Storage Threshold (maximum limit for DB storage)
- Useful for applications with unpredictable workloads
- Supports all RDS database engines

### Read Replicas

- Create up to 5 read replicas
- Within AZ, cross AZ or cross region
- Replication is ASYNC so reads are eventually consistent
- Replicas can be promoted to their own DB
- Applications must update the connection string to leverage read replicas

- The production application is unaffected
- Read replicas are used for SELECT statements

- For RDS read replicas within the same region, you don't pay that fee

### Multi AZ (Disaster Recovery)

- SYNC replication
- One DNS name - automatic app failover to standby
- Increase availability
- Failover in case of loss of AZ, loss of network, instance or storage failure
- No manual intervention in apps
- Not used for scaling

- RDS from Single-AZ to Multi-AZ
	- Zero downtime operation
	- Just click on modify
	- The following happens internally: 
		- A snapshot is taken
		- A new DB is restored from the snapshot in a new AZ
		- Synchronization is established between the two databases

### RDS Security - Encryption

  - At rest encryption
    - Possibility to encrypt the master and read replicas with AWS KMS - AWS-256 encryption
    - Encryption has to be defined at launch time
    - If master is not encrypted, the read replicas cannot be encrypted
    - Transparent Data Encryption (TDE) available for Oracle and SQL Server

  - In-flight encryption
    - SSL Certificates to encrypt data to RDS in flight
    - Provide SSL options with trust certificate when connection to database
    - To enforce SSL:
      - PostgreSQL: rds.force_ssl=1 in the AWS RDS Console (Parameter Groups)
      - MySQL: within the DB Command
      
  - Operations

    - Encrypting RDS Backups
      - Snapshots of un-encrypted RDS databases are un-encrypted
      - Snapshots of encrypted RDS Databases are encrypted
      - Can copy a snapshot into an encrypted one
    
    - To encrypt an un-encrypted RDS database
      - Create a snapshot of the un-encrypted database
      - Copy the snapshot and enable encryption for the snapshot
      - Restore the database from the encrypted snapshot
      - Migrate apps to the new database, and delete the old database
    
  - Network & IAM

    - Network Secutiry
      - RDS databases are usually deployed within a provate subnet, not in a public one
      - RDS security works by leveraging security groups (the same concept as for EC2 instances) - it controls 
      which IP / security group can communicate with RDS
    
    - Access Management
      - IAM policies help control who can manage AWS RDS (through the RDS API)
      - Traditional Username and Password can be used to login into the database
      - IAM-based authentication can be used to login into RDS MySQL and PostgreSQL
    
    - IAM Authentication
      - Works with MYSQL and PostgreSQL
      - Don't need a password, just an auyuthentication token obtained through IAM and RDS API calls
      - Auth token has a lifetime of 15 minutes

      - Benefits
        - Network in/out must be encrypted using SSL
        - IAM to centrally manage users instead of DB
        - Can leverage IAM Roles and EC2 Instance profiles for ease integration

### Summary

  - Encryption ar rest
    - Is done only when you first create the DB instance
    - or: unencrypted DB -> snapshot -> copy snapshot as encrypted -> create DB from snapshot

  - Your responsibility: 
    - Check the ports / IP / security groups inbound rules in Db's SG
    - In-database user creation and permissions or manage through IAM
    - Creating a database with or without public access
    - Ensure parameter group or DB is configured to only allow SSL connections

  - AWS responsibility
    - No SSH access
    - No manual DB and OS patching
    - No way to audit the underlying instance
  