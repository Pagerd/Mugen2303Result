### oe_test_storage_DevMgmt_lsblk：分区表异常

riscv上相关报错为

```
+ mkfs.ext4 -F /dev/
mke2fs 1.46.5 (30-Dec-2021)
mkfs.ext4: Device size reported to be zero.  Invalid partition specified, or
	partition table wasn't reread after running fdisk, due to
	a modified partition being busy and in use.  You may need to reboot
	to re-read your partition table.

+ CHECK_RESULT 1
```

x86相关报错为

```
+ mkfs.ext4 -F /dev/sr0
mke2fs 1.46.5 (30-Dec-2021)
mkfs.ext4: No medium found while trying to determine filesystem size
```

