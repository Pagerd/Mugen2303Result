### oe_test_service_arptables

单独测试时的报错和统一测试时的报错不一样，为找不到内核模块

```
[root@openeuler-riscv64 mugen]# arptables
modprobe: FATAL: Module arp_tables not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
arptables v0.0.5: can't initialize arptables table `filter': arptables who? (do you need to insmod?)
Perhaps arptables or your kernel needs to be upgraded.
```

## 