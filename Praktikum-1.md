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
![ubuntu_landing](assets/ubuntu_landing.png)
2. Install lxc debian 9 dengan nama debian_php5.6
  - Kunjungi https://uk.images.linuxcontainers.org/ untuk melihat image yang akan dibuat.
  - installation command
```bash
sudo lxc-create -n debian_php5.6 -t download -- --dist debian --release sid --arch amd64 --no-validate --server uk.images.linuxcontainers.org
```
![ubuntu_landing](assets/debian_php5.6.png)
3. Setup nginx pada debian_php5.6 untuk domain http://lxc_php5.dev , buat halaman index.html yang menerangkan informasi nama lxc
