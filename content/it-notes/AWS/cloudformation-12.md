# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [CFN-Init](#CFN-Init)
  - [EC2 User Data](#CFN-Init#EC2 User Data)

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
  
