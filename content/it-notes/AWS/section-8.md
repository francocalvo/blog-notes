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

</div>
{{<toc>}}

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
