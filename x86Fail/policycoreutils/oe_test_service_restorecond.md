### oe_test_service_restorecond：服务启动失败：未找到服务项

riscv与x86报错均相同

对应报错log如下

```
+ systemctl restart restorecond.service
Failed to restart restorecond.service: Unit restorecond.service not found.
+ CHECK_RESULT 5 0 0 'restorecond.service restart failed'
```

