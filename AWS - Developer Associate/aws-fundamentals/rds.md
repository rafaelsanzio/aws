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