# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)

</div>
{{<toc>}}

Conditions are used to control the creation of resources or outputs based on a
condition, allowing to create different resources or properties depending on
the environment for example.

To define a condition we do:

```YAML
Conditions:
  CreatesProdResources: !Equal [ !Ref EnvType, prod ]
```

Here, the logical ID is for you to choose, where we name our condition.
The intrinsic function can be:
- `Fn::And`     
- `Fn::Equals` 
- `Fn::If` 
- `Fn::Not` 
- `Fn::Or` 

We can use it like this, to create a resource conditionally:

```YAML
Resources:
  MountPoint:
    Type: AWS::EC2::VolumeAttachment
    Condition: CreateProdResources
```

If this condition is false, it won't be created.

