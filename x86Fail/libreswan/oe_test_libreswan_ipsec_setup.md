# oe_test_libreswan_ipsec_setup

x86 和 riscv 失败原因一致

``ipsec setup`` 启动停止超时

```
+ SLEEP_WAIT 2 'ipsec setup --start'
+ wait_time=2
+ cmd='ipsec setup --start'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 2 --cmd 'ipsec setup --start' --mode 1
Redirecting to: systemctl start ipsec.service
Fri Jul 21 01:35:35 2023 - ERROR - Timeout : Command 'ipsec setup --start' timed out after 1.9988475960001324 seconds

+ SLEEP_WAIT 2 'ipsec setup --stop'
+ wait_time=2
+ cmd='ipsec setup --stop'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 2 --cmd 'ipsec setup --stop' --mode 1
Redirecting to: systemctl stop ipsec.service
Fri Jul 21 01:35:44 2023 - ERROR - Timeout : Command 'ipsec setup --stop' timed out after 1.9990322969999852 seconds

+ SLEEP_WAIT 2 'ipsec setup --restart'
+ wait_time=2
+ cmd='ipsec setup --restart'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 2 --cmd 'ipsec setup --restart' --mode 1
Redirecting to: systemctl restart ipsec.service
Fri Jul 21 01:35:50 2023 - ERROR - Timeout : Command 'ipsec setup --restart' timed out after 1.9991150970001854 seconds
```

