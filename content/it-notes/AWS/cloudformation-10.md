# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Rules](#Rules)
  - [Example](#Rules#Example)

</div>
{{<toc>}}

# Rules

This allows us to do parameter validations based on the values of other
parameters. For example, ensure that all subnets selected are within the same
VPC.

Each rule consists of:

- **Rule condition:** it's optional, and determines when a rules takes effect.
- **Assertions:** describes what values are allowed for a particular parameter.
  Can contain mor than one asset.

```YAML
Rules:
  Rule01:
    Assertions:
      - Assert:
        rule-specific intrinsic function: Value01
        AssertDescription: Information about this assert.
  Rule02:
    RuleCondition:
      rule-specific intrinsic function: Value02
    Assertions:
      - Assert:
        rule-specific intrinsic function: Value03
        AssertDescription: Information about this assert.
      - Assert:
        rule-specific intrinsic function: Value04
        AssertDescription: Information about this assert.
```

## Example

If you have an Application Load Balancer that has a SSL listener, you might want 
to enforce users to provide an ACM certificate ARN.

```YAML
  Rules:
    RuleCondition: !Equals
      - !Ref UseSSL
      - Yes
    Assertions:
      - Assert: !Not
        - !Equals
          - !Ref ALBSSLCertificateARN
          - ''
      AssertDescription: "ACM certificate value can not be empty if SSL is
        required."
```

The functions used to define a Rule condition and assertions, and their result
needs to be True or False. They are:

- `Fn::And` 
- `Fn::Contains` 
- `Fn::EachMemberEquals` 
- `Fn::EachMemberIn` 
- `Fn::Equals` 
- `Fn::If` 
- `Fn::Not` 
- `Fn::Or` 
- `Fn::RefAll` 
- `Fn::ValueOf` 
- `Fn::ValueOfAll` 


