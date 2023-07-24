### oe_test_service_radvd：服务启动失败或未找到

riscv对应报错如下

```
+ systemctl restart radvd.service
Job for radvd.service failed because the control process exited with error code.
See "systemctl status radvd.service" and "journalctl -xeu radvd.service" for details.
```

x86在尝试启动时就发生错误

```
× radvd.service
     Loaded: not-found (Reason: Unit radvd.service not found.)
     Active: failed (Result: exit-code) since Thu 2023-05-04 23:27:36 UTC; 11s ago
```

