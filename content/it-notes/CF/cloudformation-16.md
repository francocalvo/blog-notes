---
title: 16. CF Deployment Options
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [ChangeSets](#ChangeSets)
- [Stack Creation Failures](#Stack Creation Failures)
- [Rollback triggers](#Rollback triggers)

</div>
{{<toc>}}

# ChangeSets

When we update a stack, this allow us to see what changes will happen before
applying them. It won't tell us whether the update will be successful.

We can create a ChangeSet when we are creating/updating a stack, an it'll show
the changes.

This will put the stack in a "Review in progress" status, which we can act on
in the "Change sets" tab.

# Stack Creation Failures

If a CF stack fails, it will get to a `ROLLBACK_COMPLETE`. This means CF tried
to create some resources but one failed, so it rolled back all the changed.

# Rollback triggers

This enables CF to rollback stack operations if that operations triggers a
CloudWatch Alarm. This alarm can be monitores during:

- Stack create/update.
- The monitoring period from 0 to 180 minutes.

If any of the alarmas goes to the `ALARM` state, CF will roll back the entire
operation.
