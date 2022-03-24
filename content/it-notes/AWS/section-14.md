# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Important Links](#Important Links)
  - [Deploying templates](#Important Links#Deploying templates)
  - [Bulding Blocks](#Important Links#Bulding Blocks)
- [Resources](#Resources)
- [Parameters](#Parameters)
  - [The Ref function](#Parameters#The Ref function)
  - [Pseudo Parameters](#Parameters#Pseudo Parameters)
- [Mappings](#Mappings)
  - [Function `FindInMap`](#Mappings#Function `FindInMap`)
- [Outputs](#Outputs)
- [Conditions](#Conditions)
- [Others](#Others)
  - [Functions](#Others#Functions)
  - [CloudFormation Rollbacks](#Others#CloudFormation Rollbacks)
  - [ChangeSets](#Others#ChangeSets)
  - [Nested stacks](#Others#Nested stacks)
  - [StackSets](#Others#StackSets)
- [CloudFormation Drift](#CloudFormation Drift)
- [Example](#Example)
- [Extra course in CloudFormation](#Extra course in CloudFormation)

</div>
{{<toc>}}

# Important Links

- [Docs on ApiGateway::RestApi](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-apigateway-restapi.html)


works like:

- Templates have to be uploaded in S3 and then referenced in CloudFormation.
- To update a template, we can't edit previous ones, we have to re-upload a new
  version of the template to AWS.
- Stacks are identified by a name, and deleting a stack deletes every artifact
  that was created by CloudFormation.

## Deploying templates

There are two ways:

- **Manual way:** consists of editing templates in the CloudFormation Designer,
  and using the console to input parameters, etc.
- **Automated way:** editing templates in a YAML file and using AWS CLI to
  deploy templates.

## Bulding Blocks

The templates components:

1. **Resources:** your AWS resources declared in the template. (MANDATORY)
2. Parameters: the dynamic inputs for your template.
3. Mappings: the static variables for your template.
4. Outputs: references to what has been created.
5. Conditionals: list of conditions to perform resource creation.
6. Metadata.

For template helpers, you can also have functions and references.

Cloudformation is smart enough that it know what to create first, for example,
if you have a virtual machine and a security group, it'll always create the
security group first.

Also, when you update it, it'll scan for the changes and show them to you
before update.

# Resources

These are the core of your CloudFormation template, and they represent the
different AWS Components that will be created and configured. There are
declared and can reference each other, like a security group and a EC2.

Normally, their identification are in the form of:
`AWS::aws-product-name::data-type-name` 

The docs can be found [here](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html). We can see here all the different resources and all their propertioes.

It's important to know that you can't create dynamic amount of resources, and
that there are some services not supported.

# Parameters

Parameters are a way to provide inputs to your AWS CloudFormation template.
They are important if you want to reuse your template or some inputs can't be
determined ahead of time.

You use this when is a resource configuration that's repeated or that you might
want to change in the future.
 
It can have all these settings:

```YAML
Type:
  String
  Number
  CommaDelimitedList
  List<Type>
AWS Parameter
ConstraintDescrpition
Min/MaxLength
Min/MaxValue
Defaults
AllowedValues (array)
AllowedPattern (regexp)
NoEcho (boolean)
```

## The Ref function

To reference a parameter, you use a function called `Fn::Ref`. This function
can be use to invoke both parameters or resources, as we se in the `MyInstance`
resource, in the `SecurityGroups`, as seen in the example.

## Pseudo Parameters

AWS offers us pseudo parameters in any CloudFormation, like:

- `AWS::AccountId` 
- `AWS::NotificationARNs` 
- `AWS::NoValue` 
- `AWS::Region` 
- `AWS::StackId` 
- `AWS::StackName` 

These can be used at any time and are enabled by default.

# Mappings

Mappings are fixed variables within your CloudFormation template. They are very
handy to differentiate between environments, regions, etc.
An example of how it's seen:

```YAML
Mappings:
  Mapping01:
    Key01:
      Name: Value01
    Key02:
      Name: Value02
    Key03:
      Name: Value03
```

This values are hardcoded is "low-level". They are great when you know in
advance all the values that can be taken, as the allow safer control over the
template.

## Function `FindInMap` 

To call these mappings, we use `Fn::FindInMap` to return a named value from a
specific key. It's syntax is: 
`!FindInMaP [ MapName, TopLevelKey, SecondLevelKey ]` 

We can even used nested mappings or references in the command to make it more
complex.

# Outputs

The output section declared optional outputs values that we can import into
other stacks. These can be seen in the console or CLI. They are useful as it
allows us to see IDs an other variables being used, and it's excellent for
collaboration cross stack.

It's important that you can't delete a stack if its output is being referenced
by another stack.

An example of how it looks like:

```YAML
Outputs:
  StackSSHSecurityGroup:
    Descrpition: The SSH Security Group of the company
    Value: !Ref MySSHSecGroup
    Export:
      Name: SSHSecGroup
```

This allows other stacks to access the `SSHSecGroup` from another stack, using
the `Fn::ImportValue` function. For example, in a second template we could:

```YAML
Resources:
  MySecureInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-a4c7edb2
      InstanceType: t2.micro
      SecurityGroups:
        - !ImportValue SSHSecGroup
```

# Conditions

Conditions are used to control the creation of resources or outputs based on a
condition. They can be whatever, but commons are environment, region, or
another parameter value.

It looks like:

```YAML
Conditions:
  CreateProdResources: !Equals [ !Ref EnvType, prod ]
```

The logical functions are `And`, `Equals`, `If`, `Not` and `Or`, and these can
be applied to resources, outputs, etc. For example, in a resource, you can
define it directly beneath the `Type`.

# Others

## Functions
Intrinsic being resumed are:

- `Ref`: can be leveraged to reference parameters or resources.
- `GetAtt`: attributes are attached to all resources, and it allows us to get
  them.
- `FindInMap`: to return a named value from a specific key.
- `ImportValue`: import values are exported to another template.
- `Join`: joins values with a delimiter that we can specify.
- `Sub`: it's used to substitute variables from a text. The sting must have
  `${Variable}` and it will be substituted.

## CloudFormation Rollbacks

When a stack creation/update fails, it will by default roll back to the
previous state and delete the new one. We can look at the log. You can disable
this behavior to troubleshoot.

## ChangeSets

When you update a stack, you need to know what changes before it happens for
greater confidence. They won't say if the update will be successful.

## Nested stacks

There are stacks of other stacks. They allow us to isolate repeated patterns in
different stacks and call them multiple times. To update them, you need to
update the parent.

## StackSets

It allows to create, update or delete stacks across multiple accounts and
regions with a single operation. Trusted accounts can use them.

When you update a stack set, all associated stack instances are updated
throughout all account and regions.

# CloudFormation Drift

CF allows us to create infra, but it doesn't protect us against manual
configurations changes like in the CLI. When this happens, we say our resources
have been **drifted**.

We can use CloudFormation Drift to protect us from this.

After we create a template, we can use the function in the console 
`Stack Actions -> Detect Drift`, which will return the *Drift Status*, which
will show us the expected JSON and the actual one.


---

# Example

```YAML
---
Parameters:
  SecurityGroupDescription:
    Description: Security Group Description
    Type: String

Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-a4c7edb2
      InstanceType: t2.micro
      SecurityGroups:
        - !Ref SSHSecurityGroup
        - !Ref ServerSecurityGroup

  # an elastic IP for our instance
  MyEIP:
    Type: AWS::EC2::EIP
    Properties:
      InstanceId: !Ref MyInstance

  # our EC2 security group
  SSHSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: Enable SSH access via port 22
      SecurityGroupIngress:
      - CidrIp: 0.0.0.0/0
        FromPort: 22
        IpProtocol: tcp
        ToPort: 22

  # our second EC2 security group
  ServerSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: !Ref SecurityGroupDescription
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: 80
        ToPort: 80
        CidrIp: 0.0.0.0/0
      - IpProtocol: tcp
        FromPort: 22
        ToPort: 22
        CidrIp: 192.168.1.1/32
```

---

# Extra course in CloudFormation

5. [CloudFormation Parameters](CloudFormation-5)
6. [CloudFormation Resources](cloudformation-6)
7. [CloudFormation Mappings](cloudformation-7)
8. [CloudFormation Outputs](cloudformation-8)
9. [CloudFormation Conditions](cloudformation-9)
10. [CloudFormation Rules](cloudformation-10)
11. [CloudFormation Metadata](cloudformation-11)


12. [Nested Stacks](cloudformation-14)
