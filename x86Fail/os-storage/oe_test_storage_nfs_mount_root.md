### oe_test_storage_nfs_mount_root:ssh连接失败/没有安装预装软件

riscv在测试ssh时报错

```
1 packets transmitted, 0 received, 100% packet loss, time 0ms
Fri Apr 28 08:04:46 2023 - ERROR - connection to 10.198.114.3 failed.
```

而x86则没有iptables，因此测试失败

```
+ iptables -F
oe_test_storage_nfs_mount_readonly.sh: line 25: iptables: command not found
```

