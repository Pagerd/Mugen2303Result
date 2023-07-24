### oe_test_openvpn：多数命令报错

riscv与x86上均有很多未通过命令

```
+ nohup openvpn --local 127.0.0.1 --config tt.vpn --dev tun1 --ifconfig 10.4.0.1 10.4.0.2 --verb 9
+ pgrep -f 'openvpn --local'
+ CHECK_RESULT 1
```

```
+ ping -c 3 10.4.0.1
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

```
+ nohup openvpn --remote 10.198.114.6 --dev tun1 --ifconfig 10.4.0.1 10.4.0.2 --verb 9
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

```
 P_SSH_CMD --node 2 --cmd 'ping -c 3 10.4.0.1 >/dev/null'
+ python3 /root/mugen/libs/locallibs/ssh_cmd.py --node 2 --cmd 'ping -c 3 10.4.0.1 >/dev/null'

+ CHECK_RESULT 1
+ actual_result=1
```

