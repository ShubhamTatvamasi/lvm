# lvm

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

Create Phisical Volume from a disk:
```bash
pvcreate /dev/xvdc
```

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



