# oe_test_service_ipmievd

x86 和 riscv 失败原因基本一致

ipmievd.service 启动失败

```
+ journalctl --since '2023-06-02 10:18:44' -u ipmievd.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
Jun 02 10:18:44 localhost.localdomain systemd[1]: ipmievd.service: Control process exited, code=exited, status=1/FAILURE
Jun 02 10:18:44 localhost.localdomain systemd[1]: ipmievd.service: Failed with result 'exit-code'.
Jun 02 10:18:44 localhost.localdomain systemd[1]: Failed to start Ipmievd Daemon.
Jun 02 10:18:56 localhost.localdomain systemd[1]: ipmievd.service: Control process exited, code=exited, status=1/FAILURE
Jun 02 10:18:56 localhost.localdomain systemd[1]: ipmievd.service: Failed with result 'exit-code'.
Jun 02 10:18:56 localhost.localdomain systemd[1]: Failed to start Ipmievd Daemon.
```

x86 内核缺少 ipmi_si 内核模块

riscv 内核缺少 ipmi_watchdog 、 ipmi_poweroff 、 ipmi_devintf 、 ipmi_si 、 ipmi_msghandler 内核模块

