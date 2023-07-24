### oe_test_service_iscsiuio：启动服务失败

riscv上为重启服务时报错

```
+ systemctl restart iscsid.service
Job for iscsid.service failed because the control process exited with error code.
See "systemctl status iscsid.service" and "journalctl -xeu iscsid.service" for details.
+ CHECK_RESULT 1 0 0 'iscsid.service restart failed'
```

x86上则找不到该服务

```
+ systemctl restart iscsiuio.service
Failed to restart iscsiuio.service: Unit iscsiuio.service not found.
+ CHECK_RESULT 5 0 0 'iscsiuio.service restart failed'
```

