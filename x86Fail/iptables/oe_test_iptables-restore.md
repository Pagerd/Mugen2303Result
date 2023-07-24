# oe_test_iptables-restore

测试套问题， x86 和 riscv 失败原因一致

测试套 Line 32-40 如下

```
    iptables-save > iptables_bak
    echo "*filter
-A INPUT -p icmp -j DROP
COMMIT" > iptables_rule
    iptables-restore -t iptables_rule
    CHECK_RESULT $? 0 0 "iptables-restore -t exec fail"
    iptables-restore -n iptables_rule
    iptables -nvL | grep "DROP       icmp"
    CHECK_RESULT $? 0 0 "iptables-restore -n exec fail"
```

``grep "DROP       icmp"`` 失败， ``ip6tables -nvL`` 输出如下

```
# iptables -nvL
Chain INPUT (policy ACCEPT 7 packets, 376 bytes)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 DROP       1    --  *      *       0.0.0.0/0            0.0.0.0/0           

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         

Chain OUTPUT (policy ACCEPT 6 packets, 592 bytes)
 pkts bytes target     prot opt in     out     source               destination
```

