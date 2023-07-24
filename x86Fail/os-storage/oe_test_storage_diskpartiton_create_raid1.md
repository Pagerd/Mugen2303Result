### oe_test_storage_diskpartiton_create_raid1:挂载了错误的磁盘

riscv在挂载时显示不是一个磁盘

下为报错log

```
mdadm: Note: this array has metadata at the start and
    may not be suitable as a boot device.  If you plan to
    store '/boot' on this device please ensure that
    your boot-loader understands md/v1.x metadata, or use
    --metadata=0.90
mdadm: /dev/ is not a block device.
```

x86显示没有找到对应的磁盘

```
+ mdadm --create --auto=yes /dev/md0 --level=0 --raid-device=3 /dev/sr0 /dev/vdb /dev/vdc
mdadm: cannot open /dev/sr0: No medium found
```

