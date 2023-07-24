### oe_test_storage_ext3_resize：指定的分区size为0

riscv上报错的log如下

```
+ mkfs.ext3 -F /dev/vdb1
mke2fs 1.46.5 (30-Dec-2021)
mkfs.ext3: Device size reported to be zero.  Invalid partition specified, or
	partition table wasn't reread after running fdisk, due to
	a modified partition being busy and in use.  You may need to reboot
	to re-read your partition table.

```

x86上报错的log如下

```
+ e2fsck -y /dev/sr01
e2fsck 1.46.5 (30-Dec-2021)
e2fsck: Attempt to read block from filesystem resulted in short read while trying to open /dev/sr01
Could this be a zero-length partition?
+ CHECK_RESULT 8
```

