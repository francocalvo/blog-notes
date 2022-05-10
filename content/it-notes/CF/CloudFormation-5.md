---
title: 05. CF Parameters
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)

</div>
{{<toc>}}

Parameters are a way to provide inputs to your AWS CloudFormation template.
They are useful to reuse the same template across various stacks.

Settings that can be used with it are:

- Type:
  - String.
  - Number.
  - CommaDelimitedList.
  - List<Number>.
  - AWS-Specific Parameter.
  - List<AWS-Specific-Parameter>
  - SSM Parameter.
- Description.
- ConstraintDescription.
- Min/MaxLength.
- Min/MaxValue
- Default.
- AllowedValues.
- AlloewPattern.
- NoEcho

Also, to reference them in a template we can use the `Fn::Ref` function, or
`!Ref` as a shortcut.
