# FTP-server-install
installasi server FTP pada linux OS Ubuntu 20.04 (focal fossa)

masuk ke mode super user (sudo)

```bash
sudo su
```

update repository

```bash
apt-get update
```
install package vsftpd

```bash
apt-get install vsftpd -y
```
backup konfigurasi ftp dengan perintah

```bash
cp /etc/vsftpd.conf /etc/vsftpd.conf.default
```
konfigurasi ftp server dengan masuk ke file konfigurasi di

```bash
nano /etc/vsftpd.conf
```

lalu ubah parameter sebelumnya menjadi seperti dibawah

```
SEBELUM                   SESUDAH
listen=NO                 listen=yes
# write_enable=YES        write_enable=YES
# chroot_local_user=YES   chroot_local_user=YES
```

lalu tambahkan lagi perintah dibawah pada end page

```
userlist_enable=YES
userlist_file=/etc/vsftpd.user_list
userlist_deny=No
```

simpan konfigurasi dengan menekan tombol kombinasi `CTRL + X`. jika sudah silakan teman-teman tambahkan new account pada ftp dengan perintah.

```bash 
adduser ftpuser
```

masukkan password dan confirm password. 
