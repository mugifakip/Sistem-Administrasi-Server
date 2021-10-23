# Praktikum 1 Virtualisasi
## Linux Container Commands Tab
```bash
lxc-ls
lxc-start
lxc-start -d
lxc-console
lxc-stop
lxc-clone <source> <target>
lxc-create -t <template> -f <config file>
lxc-destroy

lxc-execute -n <name> -- <command>  # Run command in new container
lxc-attach  -n <name> -- <command>  # Run command in running container

lxc-monitor    # Monitor containers for state changes
lxc-wait       # Wait for a state change
lxc-info       # Give details on a container

lxc-freeze
lxc-unfreeze

lxc-netstat
lxc-ps
```
1. Rename ubuntu_php5.6 menjadi ubuntu_landing, serta rubah IP mengikuti skema yang baru.

