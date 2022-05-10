---
title: 12. CFN-Init
--- 

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [CFN-Init](#CFN-Init)
  - [EC2 User Data](#CFN-Init#EC2 User Data)
  - [CloudFormation Init](#CFN-Init#CloudFormation Init)
  - [CloudFormation Authentication](#CFN-Init#CloudFormation Authentication)
  - [CreationPolicy](#CFN-Init#CreationPolicy)

</div>
{{<toc>}}

# CFN-Init

Many of the CF templates will be about provisioning computing resources in your
AWS Cloud. These can be EC2, Auto Scaling Groups, etc.

Usually, you want these to be self configured. We can do this with CF Init.

## EC2 User Data

Let's say we want our instance to have PHP and MariaDB installed on it. For
this we would need to write a user-data script, which will be executed at the
first boot of the instance.

We can get to do this by defining a new property like this:

```YAML
Properties:
  UserData:
    Fn::Base64: |
      script
```

## CloudFormation Init

We can do this more *Ansible-like*, where the configuration is easier to do, etc.
This is done by **CloudFormation Helper Scripts**, that are 4 Python Scripts
that come directly installed on Amazon Linux 2 AMI, or can be installed. The
services are:

- `cfn-init`: used to retrieve and interpret the resource metadata, installing
  packages, creating files and starting services. 
- `cfn-signal`: a simple wrapper to signal with a CreationPolicy or
  WaitCondition, enabling you to sync other resources in the stack.
- `cfn-get-metadata`: a wrapper script making it easy to retrieve either all
  metadata defined for a resource or path to a specific key or subtree of the
  resource metadata.
- `cfn-hup`: a daemon to check for updates to the metadata and execute custom
  hooks when the changes are detected.
  
Normally you use `cfn-init`, then `cfn-signal` and lastly `cfn-hup`.

These scripts look like this:

```YAML
Resources:
  Type: AWS::EC2::Instance
  Metadata:
    AWS::CloudFormation::Init:
      config:
        packagees:
          rpm:
            epel: "url"
          yum:
            php: []
          rubygems:
            chef:
             - "0.10.2"
        groups:
          groupOne: {}
          groupTwo:
            gid: "45"
        users:
          calvo:
            group:
              - "groupOne"
            uid: "50"
            homeDir: "/tmp"
        sources:
          /etc/myapp: "https://s3.amazonaws.com/bucket/app.tar.gz"
          /etc/repo: "https://github.com/user/repo/tarball/main"
        files:
          /tmp/setup.mysql:
            content: !Sub |
              codeline
              codeline
            mode: "000644"
            owner: "root"
            group: "root"
            source: "url"
            authentication: !testBasic
        commands:
          test:
            command: "echo hi > test.txt"
            cwd: "/"
            test: "test ! -e ~/test.txt"
            ignoreErrors: "false"
        services:
          :
  Properties:
    :
```
  
Where we got:

- Packages: used to download and install pre-packaged apps on Linux/Windows.
- Groups: define user groups.
- Users: define users and their groups.
- Sources: download files and archives and place them on the EC2 instance. It's
  very handy to download projects or scripts in Github or S3 for example. The
  supported formats are tar, tar+gzip, tar+bz2 or zip.
- Files: create files on the EC2 instance, using inline or can be pulled from a
  URL.
- Commands: run a serie of commands.
- Services: launch a list sysinit.

You could have more than one config, meaning you can create a **configSet**
with multiple configs and invoke them from the EC2 user-data. 

## CloudFormation Authentication

This allows us to define auth credentials for both Sources and Files in the 
`CloudFormation::Init`. It's recommended to use Roles instead of access and
secret keys.

```YAML
AWS::CloudFormation::Authentication:
  testBasic:
    type: basic
    uris:
      - "example.com/test"
    username: !Ref Username
    password: !Ref Password
  testS3:
    type: S3
    buckets:
      - "myS3Bucket"
    accessKeyId: !Ref accessKeyId
    secretKey: !Ref secretAccessKey
    roleName: !Ref InstanceRole
```

## CreationPolicy

This prevents a resource's status from reaching completeness until CF receives
either:
- A specified amount of success signals.
- A timeout period.

For this we can use a `cfn-signal` helper script to signal a resource. Normally
this can be done to an EC2 instance, an AutoScalingGroup or an AppStream Fleet,
for example. 
