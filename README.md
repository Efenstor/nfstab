# nfstab

A small shell script (hopefully Bourne shell-compatible) and an even smaller systemd unit file for mounting NFS shares on system boot in a better way than fstab. It is particularly useful in the following scenarios:

1. When using a network card (e.g. wi-fi) which takes some time until the actual connection becomes available
2. If NFS shares are located on temporarily offline server and you want the shares to automatically appear once the server becomes online

## Installation

```
cp nfstab /etc
cp nfstab_mount /etc
cp nfstab_mount.service /etc/systemd/system
```

Then edit /etc/nfstab according to your needs, then do:

```
systemctl enable nfstab_mount.service
systemctl start nfstab_mount.service
```