### oe_test_socket_iscsiuio：启动服务失败

riscv上为重启服务时报错

```
+ systemctl restart iscsiuio.socket
Failed to restart iscsiuio.socket: Transport endpoint is not connected
See system logs and 'systemctl status iscsiuio.socket' for details.
```

x86上则找不到该服务

```
+ systemctl restart iscsiuio.socket
Failed to restart iscsiuio.socket: Unit iscsiuio.socket not found.
+ CHECK_RESULT 5 0 0 'iscsiuio.socket restart failed'
```

