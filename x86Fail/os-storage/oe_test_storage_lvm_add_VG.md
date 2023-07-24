### oe_test_storage_lvm_add_VG：没有安装预装软件/找不到镜像

x86没有安装xgextend，导致所有测试均出错

```
+ vgextend openeulertest /dev/vdb -y
oe_test_storage_lvm_add_VG.sh: line 41: vgextend: command not found
```

riscv则报了个未找到镜像的错误

```
modprobe: FATAL: Module dm-mirror not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
  /usr/sbin/modprobe failed: 1
  Required device-mapper target(s) not detected in your kernel.
```

