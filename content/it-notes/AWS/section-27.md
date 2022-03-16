# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [AWS Step Function](#AWS Step Function)
  - [Task states](#AWS Step Function#Task states)
    - [States types](#AWS Step Function#Task states#States types)

</div>
{{<toc>}}


# AWS Step Function

This allows us to model **workflows as state machines**, one per workflow. It's
useful for order fulfillment, data processing, etc.

This are workflows are written in JSON, and gives you a visualization of the
execution, as well as its history.

This is a used to create orchestration of different services, which can be done
through a API Gateway, EventBridge, etc.

## Task states

Tasks state do some work in your state machine, like invoke one AWS Service or
running one activity in a EC2, for example. An example on how it looks is:

```JSON
"Invoke Lambda function": {
  "Type" : "Task",
  "Resource": "arn:aws:states::lambda:invoke"
  "Parameters": {
    "FunctionName": "arn",
    "Payload": {
    "Input.$": "$"
    }
  },
  "Next": "NEXT_STATE"
  "TimeoutSeconds": 300
}
```

### States types

We have:

- **Choice State:** test for a condition to send to a branch.
- **Fail or succeed state:** stop execution with failure or success.
- **Pass state:** simply pass its input to its output without performing work.
- **Wait state:** provide a delay for a certain amount of time or until a specified time.
- **Map state:** dynamically iterate steps.
- ***Parallel state:*** begin parallel branches of execution.
