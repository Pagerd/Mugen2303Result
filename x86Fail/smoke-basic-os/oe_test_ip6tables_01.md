### oe_test_ip6tables_01：没有预装对应软件

riscv上在执行-vL时出错

```
+ ip6tables -vL
+ grep -w eth1
+ awk '{print $5}'
+ CHECK_RESULT 1 0 0 'Failed to show rule FORWARD INPUT'
```

而x86上没有预装ip6tables

```
+ ip6tables -A INPUT -i lo -j ACCEPT
oe_test_ip6tables_01.sh: line 24: ip6tables: command not found
+ CHECK_RESULT 127 0 0 'Failed to add rule INPUT'
```

