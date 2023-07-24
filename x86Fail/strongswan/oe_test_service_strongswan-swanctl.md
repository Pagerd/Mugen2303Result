### oe_test_service_strongswan-swanctl:服务项命令失败

riscv与x86报错均相同

下为报错log

```
+ systemctl restart strongswan-swanctl.service
Failed to restart strongswan-swanctl.service: Unit strongswan-swanctl.service not found.
+ CHECK_RESULT 5 0 0 'strongswan-swanctl.service restart failed'
```

