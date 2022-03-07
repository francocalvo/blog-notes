# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Initial setup: connecting to a physical router](#Initial setup: connecting to a physical router)
  - [Connecting for the first time](#Initial setup: connecting to a physical router#Connecting for the first time)
  - [Configuration mode](#Initial setup: connecting to a physical router#Configuration mode)
    - [Interface configuration](#Initial setup: connecting to a physical router#Configuration mode#Interface configuration)
    - [The `do` command](#Initial setup: connecting to a physical router#Configuration mode#The `do` command)
    - [Common commands](#Initial setup: connecting to a physical router#Configuration mode#Common commands)
- [IOS Configuration Management](#IOS Configuration Management)

</div>
{{<toc>}}


# Initial setup: connecting to a physical router

When you want to connect to a physical router for the first time, it might not 
have an IP address. To connect to it and configure it we'll need a console cable 
and connect it to a computer.

When you start it up for the first time, it'll ask for a setup dialog. This type
of connection is also useful because it allows us to solve problems during
boot-up and when the SSH connection is unreliable. 

## Connecting for the first time

First, we need to enter the `privileged exec mode` or enabled mode to start using 
the server. This is done by using the `enable` command.
We can use the `?` after a command, it shows all possible keywords for it.

## Configuration mode

The enabled mode is useful to get information, but to configure a server you
use the `global mode` with the command `configure terminal`.

### Interface configuration

You can get to another level for a specific interface (like a ethernet port) by
using the `interface {type} {name}`. To exit this you can use the `exit` command,
which is going to drop us down to the configuration mode.

This can be done from the configuration mode, not in the enabled mode.

### The `do` command

It's normal to make mistakes by executing commands in the wrong command level.
When needing to use something from the enable mode, you can prepend a `do`
(like we do with sudo in Linux), to execute the command in the privileged exec
mode. This will work on all command levels except the enable level.

### Common commands

- `show ip interface brief`: it shows all interfaces and their status.
- `running-config`: show all the current configuration file. It can be more
  specific by using the `run` and specify which part of the code we are
  interested in, or by using a piped command.


# IOS Configuration Management

- **Running configuration**: it's the configuration that's actually being used.
- **Startup configuration**: it's the configuration that's going to be loaded
  the next time the router is rebooted.

Normally, changes made are reset on reboot unless it's specified as a
persistent change in the startup config.

Making changes persistent is done by using the command `copy run start` in the
enabled mode. This command can be copied to other places that we can see in the 
`?` command, like the flash memory, scp, etc.

To check contents from a file in the flash memory for example, we can use the
`more` command like this:

```
more flash:filename
```


