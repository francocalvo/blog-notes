# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)

</div>
{{<toc>}}

**Source:** [Intro to Amazon EventBridge]{https://www.youtube.com/watch?v=TXh5oU_yo9M}

This service allows us to create more micro-services, allowing us to decouple
applications.

In EventBridge, events are **observable**, no directed. This means that instead
of *order* an action, EventBridge updates on events, and the different part of
the logic can take action regarding that.

This is done by the use of a **event bus**, which selects abstracts the
producers and consumers of events, and selects filters them to the appropriate
downstream consumers.
