# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [AWS RDS Overview](#AWS RDS Overview)
  - [Backups](#AWS RDS Overview#Backups)
  - [Storage Auto Scaling](#AWS RDS Overview#Storage Auto Scaling)
  - [RDS Read Replicas](#AWS RDS Overview#RDS Read Replicas)
    - [Use cases](#AWS RDS Overview#RDS Read Replicas#Use cases)
  - [RDS Multi AZ](#AWS RDS Overview#RDS Multi AZ)
  - [RDS Security - Encryption](#AWS RDS Overview#RDS Security - Encryption)
    - [Snapshots](#AWS RDS Overview#RDS Security - Encryption#Snapshots)
    - [Network & IAM](#AWS RDS Overview#RDS Security - Encryption#Network & IAM)

</div>
{{<toc>}}

**Source:** [AWS Glue Tutorial for Beginners](https://www.youtube.com/watch?v=dQnRP6X8QAU)

# AWS RDS Overview

- RDS stands for Rational Database Service.
- It's a managed DB service for DB use, with SQL as query language. It allows
  to create Mostgres, MySQL, MariaDB, Oracle, Microsoft SQL and Aurora.

As RDS is a managed service, these are some of the benefits:
- Automated provisioning, OS patching.
- Continuous backups and restore to specific timestamp.
- Monitoring dashboards.
- Read replicas for improved read performance.
- Multi AZ setup for DR.
- Maintenance windows for upgrades.
- Scaling capability.
- Storage backend by EBS.

One of the main cons is that you can't SSH into your instances.

> The *Free Tier* available RDS is in the **Burstable classes**, more
> specifically the **db.t2.micro**, with 1vCPU and 1GiB.

## Backups

Backups are automatically enabled in RDS.
- Daily full backups of the database. (during maintenance window)
- Transaction logs are backed-up every 5 minutes.
- 7 days retention. (can be up to 35 days)

On the other hand, we got DB Snapshots:
- Manually triggered by the user.
- Retention of backup for as long as you want.

## Storage Auto Scaling

It helps you to incrase storage on your RDS db instance dynamically. When RDS
detects you are running out of free database storage, it scales automatically.

It helps to avoid manually scaling your database storage, and lets you set a
*Maximum Storage Threshold*. It has some neat configurations for when to scale
the storage.

## RDS Read Replicas

This helps with read scalability. With a RDS you can create up to 5 Read
Replicas within AZ, cross AZ or cross Region.

If you have a main RDS instance, what will happen is that there is going to be
an asynchronously replication of between the main RDS and the replicas. This
means that the reads are going to be somewhat consistent, unless the change in
the main RDS didn't have time to propagate. Lastly, you can **promote** one of
the replicas as their own DB. 

For this to be beneficial, you need to configure your main Application to take
advantage of all the Replicas.

### Use cases

Let's say you have a production database that is taking on a normal load. If
you want to run a reporting application to run some analytics, which could
overload the main RDS. You can create a Read Replica and run the new workload
there. In this case, the production application is unaffected.

## RDS Multi AZ

This is useful for disaster recovery. It will **SYNC** to a main RDS, but in a
different AZ. This allows you to have a unique DNS name, where there is an
automatic failover to the second RDS. This will increase availability.

This is a zero downtime operation, and you just need to click on "modify" for
the database and enable Multi-AZ.

## RDS Security - Encryption

RDS has **at reast encryption**, allowing:
- Possibility to encrypt the master & replicas with AWS KMS AES 256 encryption.
- Encryption has to be defined at launch time.
- If the master is not encrypted, the replicas can't be either.
- Transparent Data Encryption (TDE) available for SQL and Oracle.

It also has **in-flight encryption**, this is:
- SSL certs encrypt data to RDS in flight.
- Provide SSL options with trust certs when connecting to database.
- To enforce SSL, you need to do additional configs depending on the DB.

### Snapshots
To encrypt snapshots from a un-encrypted RDS, you can:
- Create a snapshot of the un-encrypted database.
- Copy the snapshot and enable encryption for the snapshot.
- Restore the database from the encrypted snapshot.
- Migrate apps to the new database and delete the old one.

### Network & IAM

About Network Security:
- RDS are usually deployed within a private subnet, not a public one.
- RDS security works by leveraging **security groups**, controlling which
  IP/sec group can communicate with RDS.

About Access Management:
- IAM policies help control who can manage AWS RDS.
- Traditional Username and Password can be used to login into the DB.
- IAM based auth can be used to login into RDS MySQL & PostgreSQL.

For IAM Auth, you would an authentication token obtained through IAM&RDS API
calls, where the auth token has a lifetime of 15 minutes.

%% TODO: Finish Aurora part.
