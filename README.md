Rsync wrapper using argparse, rsync and schedule reading from .ssh/config and works locally too.

# Installation

`pip install psync`

# How does it work like

Creates a pidfile at run while running, sigint to delete it. Not launch if running.

Reads config create sources list of objs default . Update server name. 

Interface class and implementation for ssh and local types. 

Check ssh config or read from hostname port.

Runs checking times and spawns threads for given object types.


# Config

Example:
```toml
[default]
type = "ssh"
ssh_command = "ssh -J proxyJumpServer {server}"
ssh_config = "~/.ssh/config"
hour = 0
day = 0
week = "*"
month = "*"
exclude_folder_bigger_than = "20M"
exclude_file_bigger_than = "1G"

[localhost]
type = "local"
from = "~/Projects"
to = "/media/matheus/Elements/Backups/Projects"
exclude  = ["vent/", "pycache"]

[deserver]
type = "remote"
from = "~/Projects/p1"
to = "/media/matheus/Elements/Backups/Projects/drserver/p1"
exclude  = ["vent/", "pycache"]
