### oe_test_service_qemu-guest-agent:服务重启失败

riscv与x86报错均相同

```
+ systemctl restart qemu-guest-agent.service
A dependency job for qemu-guest-agent.service failed. See 'journalctl -xe' for details.
+ CHECK_RESULT 1 0 0 'qemu-guest-agent.service restart failed'
```

