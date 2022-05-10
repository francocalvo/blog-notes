---
title: 11. CF Metadata
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
  - [Special keys](#Table of contents#Special keys)
    - [Interface](#Table of contents#Special keys#Interface)

</div>
{{<toc>}}

It's an optional section to include arbitrary YAML. For example:

```YAML
Metadata:
  Instances:
    Descrption: "Information about the instances."
  Databases:
    Descrption: "Information about the databases."
```

## Special keys

There are four special keys:

- `AWS::CloudFormation::Designer:` describes how the resources are laid out in
  your template. This is automatically added by CF Designer.
- `AWS::CloudFormation::Interface:` defines grouping and ordering of input
  parameters when they're displayed in the AWS Console.
- `AWS::CloudFormation::Authentication:` used to specify authentication
  credentials for files or sources that you specify in the next item.
- `AWS::CloudFormation::Init:` define configurations tasks for cfn-init.  
  
### Interface

Define grouping and ordering of input parameters. It looks like this:

```YAML
Metadata:
  AWS::CloudFormation::Interface:
    ParameterGroups:
      - Label:
          default: "Network configurations"
        Parameters:
          - parameter1
          - parameter2
      - Label:
          default: "Lambda configurations"
        Parameters:
          - parameter3
    ParameterLabels:
      SubnetID:
        default: "Which subnet should this be deployed to?"
```

This allows us to give a group of parameters a label to make the template more
clear. 
