# oe_test_iptables-restore_01

测试套问题， x86 和 riscv 失败原因一致

测试套 Line 32-40 如下

```
    ip6tables-save > ip6tables_bak
    echo "*filter
-A INPUT -p icmp -j DROP
COMMIT" > ip6tables_rule
    ip6tables-restore -t ip6tables_rule
    CHECK_RESULT $? 0 0 "ip6tables-restore -t exec fail"
    ip6tables-restore -n ip6tables_rule
    ip6tables -nvL | grep "DROP       icmp"
    CHECK_RESULT $? 0 0 "ip6tables-restore -n exec fail"
```

``grep "DROP       icmp"`` 失败， ``ip6tables -nvL`` 输出如下

```
# ip6tables -nvL
 
Chain INPUT (policy ACCEPT 1 packets, 96 bytes)
 pkts bytes target     prot opt in     out     source               destination         

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         

Chain OUTPUT (policy ACCEPT 2 packets, 192 bytes)
 pkts bytes target     prot opt in     out     source               destination
```

