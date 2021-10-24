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


```bash
sudo lxc-copy -n ubuntu_php5.6 ubuntu_landing
```
![ubuntu_landing](assets/ubuntu_landing.png)
------
2. Install lxc debian 9 dengan nama debian_php5.6


  - Kunjungi https://uk.images.linuxcontainers.org/ untuk melihat image yang akan dibuat.
  - installation command
```bash
sudo 
lxc-create -n debian_php5.6 -t download -- --dist debian --release sid --arch amd64 --no-validate --server uk.images.linuxcontainers.org
```
![debian_install](assets/debian_php5.6.png)
------
3. Setup nginx pada debian_php5.6 untuk domain http://lxc_php5.dev , buat halaman index.html yang menerangkan informasi nama lxc


  - Static ip debian_php5.6
```bash 
nano /etc/network/interfaces
```
![static debian](https://github.com/mugifakip/Sistem-Administrasi-Server/blob/1990abc510d834c33758c83e614369aca994f500/assets/network%20interface.png)
  - Setting Nginx Debian
```bash 
cd /etc/nginx/sites-available
nano lxc_php5.6.dev
```
![Nginx](assets/SetNginx.png)
```bash
nano /etc/hosts
```
![Nginx_hosts](assets/hosts.png)
```bash
cd /var/www/html/lxc_php5.6
nano index.php
```
![Nginx_hosts](assets/deb_5.6.png)
------

4. Config nginx ubuntu_landing
  -attach ke ubuntu landing dengan command
```bash
sudo lxc-attach -n ubuntu_landing
```
step by step bisa dilihat di showcase berikut
![landing](assets/ubuntu-landing4.1.gif)

Configurasi hosts ubuntu_landing
![landing](assets/Hosts.gif)

------

5. Set Auto Start ubuntu_landing

  - Edit config file ubuntu_server
````bash
sudo su
cd /var/lib/lxc/ubuntu_server
````
![landing](assets/ubuntu_landing_configg.gif)

  - ubuntu_landing autostarted success (sorry i made a typo on roofs -> rootf inside config)

![landing](assets/started.png)

------

6. Setup nginx pada vm.local untuk mengatur proxy_pass
   - mengakses http://vm.local akan diarahkan ke http://lxc_landing.dev
   - mengakses http://vm.local/blog akan diarahkan ke http://lxc_php7.dev
   - mengakses http://vm.local/app akan diartahkan ke http://lxc_php5.dev

![landing](assets/Config-vm.local.gif)

------

7. 
8. 
