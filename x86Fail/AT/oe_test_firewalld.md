### oe_test_firewalld

测试前没有安装firewalld，安装之后x86测试通过，riscv执行`ip6tables -t nat -L`出错：

```
[root@openeuler-riscv64 mugen]# ip6tables -t nat -L
ip6tables v1.8.9 (legacy): can't initialize ip6tables table `nat': Table does not exist (do you need to insmod?)
Perhaps ip6tables or your kernel needs to be upgraded.
```



排查发现没有ip6table_nat.ko模块：

```
[root@openeuler-riscv64 mugen]# ls /lib/modules/`uname -r`/kernel/net/ipv6/netfilter/
ip6table_filter.ko  ip6_tables.ko       ip6t_REJECT.ko     nf_reject_ipv6.ko  nft_fib_ipv6.ko    nft_reject_ipv6.ko
ip6table_mangle.ko  ip6t_ipv6header.ko  nf_defrag_ipv6.ko  nf_socket_ipv6.ko  nf_tproxy_ipv6.ko
[root@openeuler-riscv64 mugen]# ls /lib/modules/`uname -r`/kernel/net/ipv4/netfilter/
iptable_filter.ko  iptable_nat.ko  iptable_security.ko  ipt_REJECT.ko    nf_defrag_ipv4.ko  nf_reject_ipv4.ko  nft_fib_ipv4.ko    nft_reject_ipv4.ko
iptable_mangle.ko  iptable_raw.ko  ip_tables.ko         ipt_SYNPROXY.ko  nf_dup_ipv4.ko     nf_socket_ipv4.ko  nf_tproxy_ipv4.ko
```

