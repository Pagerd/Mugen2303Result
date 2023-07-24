# oe_test_service_kdump

测试套问题， x86 和 riscv 失败原因不同

测试对象 kdump.service 由 kexec-tools 软件包提供，该软件包在 x86 镜像预装了但是在 riscv 没有预装

在 riscv 失败

```
+ systemctl restart kdump.service
Failed to restart kdump.service: Unit kdump.service not found.
```

在 x86 虽然预装了，但是启动出错

```
+ journalctl --since '2023-06-07 09:21:08' -u kdump.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
Jun 07 09:21:08 localhost.localdomain systemd[1]: kdump.service: Failed with result 'signal'.
```

