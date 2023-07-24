# oe_test_libreswan_ipsec_systemctl

x86 和 riscv 失败原因一致

ipsec.service 启停超时

```
+ SLEEP_WAIT 2 'systemctl start ipsec.service'
+ wait_time=2
+ cmd='systemctl start ipsec.service'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 2 --cmd 'systemctl start ipsec.service' --mode 1
Wed Jun  7 09:46:21 2023 - ERROR - Timeout : Command 'systemctl start ipsec.service' timed out after 1.9997982299998966 seconds

+ SLEEP_WAIT 2 'systemctl restart ipsec.service'
+ wait_time=2
+ cmd='systemctl restart ipsec.service'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 2 --cmd 'systemctl restart ipsec.service' --mode 1
Wed Jun  7 09:46:26 2023 - ERROR - Timeout : Command 'systemctl restart ipsec.service' timed out after 1.9997843999999532 seconds
```

