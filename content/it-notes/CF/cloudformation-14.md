---
title: 14. Nested Stacks
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Deployment](#Deployment)
- [Updating](#Updating)
- [Cross Stacks](#Cross Stacks)

</div>
{{<toc>}}


Nested stacks that are part of other stacks. They allow you to isolate repeated
patterns common components, etc. These are considered best practice, and to
update a nested stack, you always  need to update the parent.

# Deployment

We can **output** values for others stacks inside the nested stack like this:

```YAML
Outputs:
  SSHGroupId:
    Value: !Ref SSHSecGroup
    Description: A meaningful description
```

Then we have to create a resource of the type `AWS::CloudFormation::Stack`, so
we first upload our last stack to a S3 bucket, copy its URL and create the
resource like the following. More info in the [docs](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-stack.html).

```YAML
Type: AWS::CloudFormation::Stack
Properties: 
  NotificationARNs: 
    - String
  Parameters: 
    Key : Value
  Tags: 
    - Tag
  TemplateURL: String
  TimeoutInMinutes: Integer
```

# Updating

To update a nested stack, we need to update the parent. For this, we'll need to
update a new file to a S3 Bucket and change the URL for the new one or use a
"version" of the same S3 object.

# Cross Stacks

These are helpful when stacks have different lifecycles. We can use the Outputs
Export and `Fn::ImportValue` for things like VPC Id, etc.

On the other hand, nested stacks are helpful when components must be reused. 
