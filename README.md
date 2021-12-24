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
