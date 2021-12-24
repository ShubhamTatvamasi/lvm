# lvm

### List

List Physical volumes:
```bash
pvdisplay
pvs
```

List Volume groups:
```
vgdisplay
vgs
```

List Logical volumes:
```bash
lvdisplay
lvs
```

---

### Create

Create Phisical Volume from a disk:
```bash
pvcreate /dev/xvdc
```

Create Volume group:
```bash
vgcreate vg_extra /dev/xvdc
```

Create Logical volume:
```bash
lvcreate vg_extra -L 5G -n lv_volume
```

---

### Mount Volume

Format the disk file system to ext4:
```bash
mkfs.ext4 /dev/vg_extra/lv_volume
```

Create directory to mount:
```bash
mkdir -p /mnt/extra/volume
```

Mount volume to director:
```bash
mount /dev/vg_extra/lv_volume /mnt/extra/volume
```

Unmount volume:
```bash
umount /mnt/extra/volume
```

Get ID of logical volume:
```bash
blkid /dev/vg_extra/lv_volume
```

Edit fstab file and add the mount volume:
```bash
vim /etc/fstab
```

```
UUID=6de8c7be-13b7-4b50-8a5d-130b08941bd3 /mnt/extra/volume ext4 defaults 0 2
```

Mount everything in fstab:
```bash
mount -a
```

---

### Extend

Extend existing volume group:
```bash
vgextend vg_ubuntu /dev/xvdc
```

Extend logical volume:
```bash
lvextend -L +10G /dev/mappper/vg_ubuntu-lv_root
```

Resize file system:
```bash
resize2fs /dev/mappper/vg_ubuntu-lv_root
```

Give 100% free space to the file system:
```bash
lvextend --resizefs -l +100%FREE /dev/mapper/vg_ubuntu-lv_root
```

https://www.learnlinux.tv/linux-logical-volume-manager-lvm-deep-dive-tutorial/


