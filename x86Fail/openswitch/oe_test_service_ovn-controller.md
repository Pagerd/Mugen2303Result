### oe_test_service_ovn-controller:服务启动失败

x86上为未找到该服务

```
+ service ovn-controller.service restart
Redirecting to /bin/systemctl restart ovn-controller.service
Failed to restart ovn-controller.service: Unit ovn-controller.service not found.
```

而riscv上则为无法使用service指令

```
+ service ovn-controller.service stop
oe_test_service_ovn-controller.sh: line 39: service: command not found
+ CHECK_RESULT 127 0 0 'ovn-controller.service stop failed'
```

