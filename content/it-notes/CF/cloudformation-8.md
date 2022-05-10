---
title: 08. CF Outputs
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)

</div>
{{<toc>}}

Outputs is a new section that allows us to declare *optional* outputs values
that we can import into other stacks.

They are very useful to define a network in CF, and output the variables such
as the VPC ID and your Subnet IDs.

To do **cross-stack references** we use the `Fn::importValue`, which allows us
to import a output parameter from other stack by it's key.

