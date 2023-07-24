# oe_test_service_bmc-snmp-proxy

测试套问题， x86 和 riscv 失败原因一致

测试需要 snmpd.service 和 bmc-snmp-proxy.service ，它们分别由 net-snmp 和 bmc-snmp-proxy 软件包提供

这两个软件包在 x86 和 riscv 均没有预装，且测试脚本没有显示安装，导致测试失败

```
+ systemctl start snmpd.service
Failed to start snmpd.service: Unit snmpd.service not found.

+ systemctl restart bmc-snmp-proxy.service
Failed to restart bmc-snmp-proxy.service: Unit bmc-snmp-proxy.service not found.
```

