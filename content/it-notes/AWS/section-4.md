# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [IAM](#IAM)
  - [Create users](#IAM#Create users)
  - [IAM Polices](#IAM#IAM Polices)
    - [Security](#IAM#IAM Polices#Security)
  - [Access CLI and SDK](#IAM#Access CLI and SDK)
  - [IAM Roles](#IAM#IAM Roles)

</div>
{{<toc>}}

# IAM

An **IAM** is a Identity and Access Managment, which is a service. It allows
for the creation of a **root account** and **users** and **groups**. Normally,
it's good practice that all users belong to at least a group.

This allows us to create **permissions**, which can be assigned by JSON
documents called polices.

Normally it's like:

```JSON
{
  "version:": "2021-10-17",
  Statement: [
    {
      "Effect": "Allow",
      "Action": "ec2:Descrice",
      "Resource": "*"
    }
  ]
}
```

## Create users

These are normally set globally for an account. In IAM, under 
`Access management > Users` you can click on `Add user`.

Normally, you create at least a new user for an admin and add it to a admin
group.

## IAM Polices

The creation of groups allows us to take advantage of **inheritance**, where
all members of a group get the same permissions. It's really powerful because
you can have an user in multiple groups. It consists of:

- **Version:**  policy language version. Always includes "2012-10-17"
- **ID:**  it's an identifier for the policy. Optional.
- **Statement:** one or more individual statements. It consists of:
  - *SID:*  an identifier for the statement.
  - *Effect:* whether it allows or denies access.
  - *Principal:* account/user/role to which the policy applies.
  - *Actions:* list of actions this policy allows or denies.
  - *Resource:* list of resources to which the actions are applied.
  - *Conditional:* conditions for when to use the policy.

### Security

On section 15 of the course you can have an overview of MFA and security of the
accounts. It's mainly on strong passwords and MFA. In AWS you can use a Virtual
MFA like Authy or a Universal 2nd Factor Security Key (U2F) like Yubikey.

## Access CLI and SDK

These services are other ways to access AWS which are protected by access keys.
Each user manage their own access keys, which are secrets. These are generated
through the AWS Console and you can download it and install it in any computer.

The AWS CLI allows us direct access to the public APIs of AWS services, where
you can develop scripts to manage.

On the other hand, SDK is a set of libraries what enables you to access and
manage AWS services programmatically, being embedded in your application.

To see how to download, see Lesson 18.

## IAM Roles

Sometimes, AWS services will need to perform actions on your behalf. To do so,
we will assign permissions to AWS services with IAM Roles, like to a EC2
Instance.
