# oe_test_service_rdisc

x86 和 riscv 失败原因一致，测试脚本依赖 rdisc.service 但是没有显示安装依赖的软件包，同时没有软件包提供该 systemd daemon

```
+ systemctl restart rdisc.service
Failed to restart rdisc.service: Unit rdisc.service not found.

# dnf provides */rdisc.service

Last metadata expiration check: 2:58:41 ago on Thu 20 Jul 2023 03:10:27 AM UTC.
Error: No matches found. If searching for a file, try specifying the full path or using a wildcard prefix ("*/") at the beginning.
```

