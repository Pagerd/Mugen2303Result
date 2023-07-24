### oe_test_service_openswitch-ipsec:服务启动失败

x86上为未找到该服务

```
+ service openvswitch-ipsec.service restart
Redirecting to /bin/systemctl restart openvswitch-ipsec.service
Failed to restart openvswitch-ipsec.service: Unit openvswitch-ipsec.service not found.
```

而riscv上则为没有service指令

```
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level info --message 'Start testing...'
Wed Apr 26 14:41:48 2023 - INFO  - Start testing...
+ service openvswitch-ipsec.service restart
oe_test_service_openvswitch-ipsec.sh: line 37: service: command not found
```

