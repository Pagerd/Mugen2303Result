### oe_test_glibc_getaddrinfo_01:测试套出错

riscv与x86报错相同

对应log如下

```
+ nslookup www.baidu.com
+ grep 'canonical name'
+ CHECK_RESULT 1 0 0 'Failed to execute nslookup'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Failed to execute nslookup'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Failed to execute nslookup'
+ LOG_ERROR 'Failed to execute nslookup'
+ message='Failed to execute nslookup'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Failed to execute nslookup'
Sat Apr 29 07:25:15 2023 - ERROR - Failed to execute nslookup
```

手动复现效果如下

```
[root@localhost mugen-riscv]# nslookup www.baidu.com
Server:		10.0.2.3
Address:	10.0.2.3#53

Non-authoritative answer:
www.baidu.com	canonical name = www.a.shifen.com.
Name:	www.a.shifen.com
Address: 112.80.248.75
Name:	www.a.shifen.com
Address: 112.80.248.76

```

暂未找出原因