### oe_test_storage_DevMgmt_block_drop：无法挂载/dev

riscv上报错为mount -o指令时失败

```
+ mount -o discard /dev/ /home/data
mount: /home/data: /dev is not a block device.
```

x86上则为mount -a时失败

```
+ mount -a
mount: /home/data: wrong fs type, bad option, bad superblock on /dev/vdb, missing codepage or helper program, or other error.
```

