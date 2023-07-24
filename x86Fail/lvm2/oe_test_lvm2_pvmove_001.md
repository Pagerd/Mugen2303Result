# oe_test_lvm2_pvmove_001

x86 和 riscv 失败原因不同

x86 将 /dev/sr0 也作为可用的块设备参与测试，导致测试失败

```
+ pvcreate -y /dev/sr0 /dev/
  No device found for /dev/.
  Device open 11:0 has no path names.
  Cannot use /dev/sr0: device not found
```

riscv 缺失内核模块 dm-mirror ，其他失败较多，具体查看完整日志

```
+ pvmove -q
modprobe: FATAL: Module dm-mirror not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
  /usr/sbin/modprobe failed: 1
  Required device-mapper target(s) not detected in your kernel.
```

