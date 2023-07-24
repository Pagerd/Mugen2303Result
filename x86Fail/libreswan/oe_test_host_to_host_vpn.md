# oe_test_host_to_host_vpn

x86 和 riscv 失败日志一致

测试依赖 firewalld 但是没有显式安装该包，该包在 x86 和 riscv 镜像均没有预装

```
+ P_SSH_CMD --cmd 'firewall-cmd --add-service=\"ipsec\";firewall-cmd --runtime-to-permanent' --node 2
+ python3 /root/mugen/libs/locallibs/ssh_cmd.py --cmd 'firewall-cmd --add-service=\"ipsec\";firewall-cmd --runtime-to-permanent' --node 2
bash: line 1: firewall-cmd: command not found
bash: line 1: firewall-cmd: command not found
+ CHECK_RESULT 127
```

