# Relational Database Service (RDS)

## RDS Essentials 

+ RDS is a fully managed Relational Database Service
  + It is fully managed: it does not allow access
  + Connections to the RDS database server look the same as connecting to a traditional on-premise database instance (i.e MySQL command line)
  + RDS has the ability to provision/resize hardware
  + You can enable Multi-AZ deployments for backup and high available solutions. 
  + Utilize Read Replicas (MySQL/PostgreSQL/Aurora) - to help offload hits on your primary database. 
  + OLTP Databases

+ Databases Supported by RDS
  + MySQL 
  + MariaDB
  + PostgreSQL
  + Oracle
  + MS SQL Server
  + Aurora:
    + Is a home grown Relational Database that has been forked from, and fully compatible with MySQL
    + It has five times better performance then MySQL and a lowe price point than commerical databases

+ Benefits of running RDS instead of a database on your own instance: 
  + Automatic minor updates
  + Automatic backups (point-in-time snapshots)
  + Server/Platform managed by AWS (PaaS)
  + Multi-AZ with a single click 
  + Automatic recovery in event of a failover 

## Amazon Aurora

+ MySQL or PostreSQL Compatible 
+ 5x faster than MySQL, 3x faster than PostgreSQL
+ Features: 
  + Continuous backup
  + Up to 15 read replicas across 3 AZs
  + Replication lag of single-digit milliseconds
  + Backtrack in seconds
  + Multi-Master options

## Amazon Aurora Serverless

+ Autoscaling
+ No management of instances or clusters
+ Scales to zero
+ Pay as you go: (ACUs, Storage, I/O)

## RDS Backups

+ AWS provides automated point-in-time backups against the RDS database instance
+ Automated backups are deleted once the database instance is deleted, and it cannot be recovered
+ The maximum retention period for automated snapshots is 35 days
+ Manual snapshots can be retained for as long as you want
+ Snapshots can be copied to other regions for Disaster Recovery purposes 
+ RDS Encryption - Snapshots are automatically encrypted

## RDS Read Replicas

+ Read replicas are asynchronous copies of the primary database that are used for read-only purposes (only allow "read connections")
+ When you write new data to the primary database, AWS copies it for you to the read replica 
+ You can create, and have multiple read replicas for, a primary database 
+ Cross-region read replicas are supported 
+ MySQL, MariaDB, PostgreSQL, and Aurora currently support read replicas 
+ You can monitor replication lag using CloudWatch 


## RDS Multi-AZ Failover 

+ Multi-AZ failover (Automatic AZ Failover) synchronously replicates data to a backup (stand-by) database instance located in another availability zone, but in the same region 
+ In the event of: 
  + Service outage in an availability zone
  + Primary DB instance failure 
  + Instance server type is changed 
  + Manual failover initiated 
  + Updating software version
  + AWS will automatically switch the DNS record from the primary instance to the stand-by instance. 
+ RDS backups are taken against the stand-by instance to reduce I/O freezes and slow down if Multi-AZ is enabled. 
+ In order for Multi-AZ to work, your primary database instance must be launched into a Subnet Group