# Mounting-USB-di-Linux
Tutorial Mounting dari Eksternal Disk ke Server Linux

1. Sebelum anda melakukan mounting, pastikan indentitas device storage anda.
dengan cara ketikan perintah dibawah ini & dapat menggunakan salah satu dari perintah berikut:

```
fdisk -l
```

```
ls -l /dev/disk/by-id/usb*
```

```
dmesg
```

```
lsblk
```

2. Mounting NFS

Untuk memasang sistem NFS Anda harus menginstal paket NFS client di sistem Anda.

- Instal NFS client di Ubuntu dan Debian

```
sudo apt install nfs-common
```

- Instal NFS client di CentOS dan Fedora:

```
    sudo yum install nfs-utils
```

- Instal NFS client di RHEL 8 :
```
    sudo dnf install nfs-utils
```

3. Untuk memasang perangkat USB secara manual gunakan langkah-langkah berikut:
- Membuat mount point:

```
sudo mkdir -p /media/usb
```

- Koneksikan drive USB/HDD di USB Connector Mesin anda
- Dengan asumsi bahwa drive USB menggunakan/dev/sdb1 anda dapat me-mount USB ke direktori /media/usb dengan mengetik:

```
sudo mount /dev/sdb1 /media/usb
```

- Cek Partisi apa saja yang ada di Linux anda dengan ketikan :
```
    df -h
```

4. Unmounting File System

Untuk melepaskan file system yang terpasang, gunakan perintah umount diikuti oleh direktori di mana ia telah dipasang (mount point) atau nama perangkat

- Cara unmound dengan kondisi USB biasa

```
umount DIRECTORY
```

```
umount DEVICE_NAME
```

- Cara unmound dengan kondisi USB dengan kondisi sistem NFS yang tidak lagi responds atau terjangkau (biasanya time out di jaringan).
```
umount -l DIRECTORY
```

- Cara unmound dengan kondisi USB dengan kondisi sistem NFS yang tidak lagi responds atau terjangkau (biasanya time out di jaringan).

```
umount -f DIRECTORY
```

- Selesai



