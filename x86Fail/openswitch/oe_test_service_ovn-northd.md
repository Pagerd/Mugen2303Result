### oe_test_service_openswitch-ipsec:服务启动失败

x86上为未找到该服务

```
+ service ovn-northd.service restart
Redirecting to /bin/systemctl restart ovn-northd.service
Failed to restart ovn-northd.service: Unit ovn-northd.service not found.
```

而riscv上则为没有service指令

```
+ service ovn-northd.service restart
oe_test_service_ovn-northd.sh: line 37: service: command not found
+ CHECK_RESULT 127 0 0 'ovn-northd.service restart failed'
```

