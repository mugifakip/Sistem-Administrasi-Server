# Praktikum 1 Virtualisasi
## Linux Container Commands Tab
```bash
lxc-ls
lxc-start
lxc-start
lxc-console
lxc-stop
lxc-clone 
lxc-create
lxc-destroy
lxc-execute
lxc-attach
lxc-monitor
lxc-wait
lxc-info
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
