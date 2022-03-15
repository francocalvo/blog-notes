# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
  - [Serverless](#Table of contents#Serverless)
- [Lambda](#Lambda)
- [TODO: Complete section](#TODO: Complete section)

</div>
{{<toc>}}

## Serverless

Lambda is a Serverless service, meaning that developers don't have to provision
and manage the servers anymore, being a more straightforward way to deploy code

# Lambda

The main difference with a EC2 instance is that the first it limited by RAM and
CPU, which is continuously running and wasting resources. On the other hand,
Lambda is composed of virtual functions that run on-demand with auto scaling.

The language support is: Node.js, Python, Java, C# .NET and Powershell, Golang
and Ruby. It also has a runtime API that's community supported and allows the
use of other languages like Rust. It also has some Lambda Container Images,
which need to implement the Lambda Runtime API, with ECS/Fargate as preferred.

For example, a good use would be a CRON job, that would waste a lot of
resources while it's doing nothing. You could use a *CloudWatch EventBridge* to
trigger an AWS Lambda Function every our to perform a task.

# TODO: Complete section
