---
title: 07. CF Mappings
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
  - [When to use mappings?](#Table of contents#When to use mappings?)
  - [Accessing Mapping Values](#Table of contents#Accessing Mapping Values)

</div>
{{<toc>}}

Mappings are fixed variables within your template. They are very handy to
differentiate between different environments like dev and prod. These are
hardcoded within the template.

It looks like:

```YAML
Mappings:
  RegionMap:
    us-east-1:
      HVM64: 1234
      HVMG2: 1235
    us-west-1:
      HVM64: 1236
      HVMG2: 1237
    eu-east-1:
      HVM64: 1238
      HVMG2: 1239
```

## When to use mappings?

These are great when you know in in advance all the values that can be taken
and that they can be deduced from variables such as:
- Region.
- Availability Zone.
- AWS Account.
- Environment (prod vs dev)

They also allows for safer control over the template.


## Accessing Mapping Values

For this we can use the `Fn::FindInMap` to return a named value from a specific
key. Fo the last example, we could:

```YAML
Resources:
  myEC2:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", HVM64]
      InstanceType: m1.small
```



