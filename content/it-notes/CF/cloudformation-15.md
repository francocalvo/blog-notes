---
title: 15. CF StackSets
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)

</div>
{{<toc>}}

StackSets allow us to manage stacks across multiple accounts and regions with
a single template. This means that when you update a stack set, **all**
associated stacks instances are updated.

The allowed operations are:

- **Create StackSet:** provide a template and targets.
- **Update StackSet:** updates always affect all stacks.
- **Delete stacks:** you can select and delete stacks from targets. Also, you
  can delete a target from the StackSet, which is going to de-attach it from
  it.
- **Delete StackSet:** you first must delete all stack instances to delete it.

We can also control the deployment by:
- Deployment Order.
- Max concurrent accounts.
- Failure tolerance.
- Region Concurrency.
- Retain Stacks.
