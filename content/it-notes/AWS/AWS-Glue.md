# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [AWS Glue Data Catalog](#AWS Glue Data Catalog)
  - [Database](#AWS Glue Data Catalog#Database)
  - [Crawlers](#AWS Glue Data Catalog#Crawlers)
  - [Connections](#AWS Glue Data Catalog#Connections)
- [AWS Glue Jobs](#AWS Glue Jobs)
  - [Triggers](#AWS Glue Jobs#Triggers)

</div>
{{<toc>}}


AWS is a fully managed **ETL** (extract, transform and load), making it easy to
clean, enrich and move data between data stores. It's a serverless service. It
consists of a Central Metadata Repository, called **Glue Data Catalog**, and a
**Spark ETL Engine**.

In AWS Glue you have to define **jobs** that can do the ETL tasks, which can be
done by a schedule, etc. With this, you got:

$$
\text{Data source} \xrightarrow{\text{extract}} \text{Jobs (transform data)} \xrightarrow{\text{load}} \text{Data target}
$$

# AWS Glue Data Catalog

This is a persistent metadata store, which:
- It's managed service.
- One AWS Glue Data Catalog per region.
- IAM policies.
- Can be used for data governance.

Some metadata is data location, schema, data type and classification.

## Database

This is a set of associated Data Catalog table definitions organized into a
logical group. Here we can keep tables. To create them you need to provide a
URI to a S3 bucket folder.

The AWS Glue **Tables** are the metadata definition that represents your data.
The original resides in its original place, this is just a representation of
the schema.

Folders where data is stored on S3, which are physical
entities, are mapped to **partitions**, which are logical entities, like
columns in the Glue Table.

## Crawlers

A crawler is a program that connects to a data store, progresses through a
prioritized list of classifiers to determine the schema for your data, and then
creates metadata tables in the AWS Glue Data Catalog.

## Connections

It's a Data Catalog object that contains the properties that are required to
connect to a particular data store. This allows us to bridge AWS Glue to other
services like RDS.

# AWS Glue Jobs

It's the business logic that is required to perform ETL work. It's composed of
a transformation script, data sources, and data targets. Job runs are initiated
by triggers that can be scheduled or triggered by events. Normally, these are
done with **Spark.** 

These can be done custom, but there are some good default ones.

## Triggers

This initiates an ETL Job. It can be defined on a scheduled time or an event,
like a EventBridge event.
