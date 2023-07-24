# oe_test_service_nis-domainname

x86 和 riscv 原因不同。测试依赖 hostname 软件包，但是这个包在 x86 镜像上并没有预装

x86 日志

```
+ systemctl restart nis-domainname.service
Failed to restart nis-domainname.service: Unit nis-domainname.service not found.
```

riscv 上 nis-domainname.service 启动失败

```
○ nis-domainname.service - Read and set NIS domainname from /etc/sysconfig/network
     Loaded: loaded (/usr/lib/systemd/system/nis-domainname.service; disabled; vendor preset: disabled)
     Active: inactive (dead)

Jul 20 12:59:02 openeuler-riscv64 systemd[1]: Condition check resulted in Read and set NIS domainname from /etc/sysconfig/network being skipped.
```

