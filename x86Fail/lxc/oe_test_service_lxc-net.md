# oe_test_service_lxc-net

x86 和 riscv 失败原因相同

lxc-net.service 启动失败

```
+ journalctl --since '2023-06-07 11:08:20' -u lxc-net.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
Jun 07 11:08:21 localhost.localdomain lxc-net[4489]: Failed to setup lxc-net.
Jun 07 11:08:21 localhost.localdomain systemd[1]: lxc-net.service: Main process exited, code=exited, status=1/FAILURE
Jun 07 11:08:21 localhost.localdomain systemd[1]: lxc-net.service: Failed with result 'exit-code'.
Jun 07 11:08:21 localhost.localdomain systemd[1]: Failed to start LXC network bridge setup.
Jun 07 11:08:34 localhost.localdomain lxc-net[4626]: Failed to setup lxc-net.
Jun 07 11:08:35 localhost.localdomain systemd[1]: lxc-net.service: Main process exited, code=exited, status=1/FAILURE
Jun 07 11:08:35 localhost.localdomain systemd[1]: lxc-net.service: Failed with result 'exit-code'.
Jun 07 11:08:35 localhost.localdomain systemd[1]: Failed to start LXC network bridge setup.
```

