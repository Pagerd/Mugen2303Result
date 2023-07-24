### oe_test_storage_diskpartiton_create_raid5:挂载了错误的磁盘

riscv在挂载时显示不是一个磁盘

下为报错log

```
+ mdadm --create --auto=yes /dev/md0 --level=0 --raid-device=3 /dev/vdb /dev/ /dev/
mdadm: /dev/ is not a block device.
+ CHECK_RESULT 2
```

x86显示没有找到对应的磁盘

```
+ mdadm --create --auto=yes /dev/md0 --level=0 --raid-device=3 /dev/sr0 /dev/vdb /dev/vdc
mdadm: cannot open /dev/sr0: No medium found
```

