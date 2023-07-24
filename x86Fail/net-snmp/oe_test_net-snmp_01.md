### oe_test_net-snmp_01:无法访问snmp

riscv与x86报错均相同

下为报错log

```
+ snmpset -v 2c -c public localhost SNMPv2-MIB::sysName.0 s test
Error in packet.
Reason: noAccess
Failed object: SNMPv2-MIB::sysName.0

+ snmpwalk -v 2c -c public localhost sysName
+ grep 'STRING: test'
+ CHECK_RESULT 1 0 0 'Set SNMPv2-MIB::sysName.0 fail'
+ actual_result=1
```

