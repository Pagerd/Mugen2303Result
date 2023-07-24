### oe_test_pcp_atop_02:段错误

riscv对应报错如下

```
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 7 --cmd '' --mode 1
/root/mugen/libs/locallibs/common_lib_python.sh: line 164: 81612 Aborted                 (core dumped) nohup /usr/libexec/pcp/bin/pcp-atop -j > atop_j 2>&1
```

x86无详细报错信息，对应报错log如下

```
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 30 --cmd '' --mode 1
+ nohup /usr/libexec/pcp/bin/pcp-atop -A
+ grep ACPU atop_A
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
```

