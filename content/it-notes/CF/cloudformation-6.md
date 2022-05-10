---
title: 06. CF Resources
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Optional attributes](#Optional attributes)
  - [DependsOn](#Optional attributes#DependsOn)
  - [DeletionPolicy](#Optional attributes#DeletionPolicy)

</div>
{{<toc>}}

Resources are the core of a CloudFormation template. They represent the
different AWS Components that will be created. These can reference each other
inside the same template.

# Optional attributes

- **DependsOn:** very useful to draw a dependency between two resources, like
  only create a ECS cluster after creating a ASG.
- **DeletionPolicy:** protect resources from being deleted even if the stack is
  deleted. 
- **UpdateReplacePolicy:** protects resources from being replaced during a CF
  update.
- **CreationPolicy**.
- **UpdatePolicy**.

## DependsOn

It allows to specify that the creation of a specific resource follows another.
When added to ar esource, that resource is created only after the creation of
the resource specified in the DependsOn.

This is automatically applied when using `!Ref` or `!GetAtt`.

## DeletionPolicy

Control what happens when the CF template is deleted or when a resource is
removed directly from a template. You have this options:

- **DeletionPolicy=Retain**: specify on resources to preserve/backup in case of
  CF deletes.
- **DeletionPolicy=Snapshot:** storage like resources, like EBS Volume,
  ElastiCache, etc.
- **DeletionPolicy=Delete:** it's the default one. 

