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

### Use Volume

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



