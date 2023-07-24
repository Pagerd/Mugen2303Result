# oe_test_service_mdmonitor

x86 和 riscv 失败原因一致

mdmonitor.service 启动失败

```
+ systemctl restart mdmonitor.service
Job for mdmonitor.service failed because the service did not take the steps required by its unit configuration.
See "systemctl status mdmonitor.service" and "journalctl -xeu mdmonitor.service" for details.
```

