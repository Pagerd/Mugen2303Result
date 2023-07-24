# oe_test_openjdk_appletviewer_clhsdb

riscv 上失败

失败日志

```
+ clhsdb
Error: Could not find or load main class sun.jvm.hotspot.CLHSDB
+ grep hsdb testlog
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_openjdk_appletviewer_clhsdb.sh line 42'
+ message='oe_test_openjdk_appletviewer_clhsdb.sh line 42'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_openjdk_appletviewer_clhsdb.sh line 42'
Fri Jul 21 01:06:25 2023 - ERROR - oe_test_openjdk_appletviewer_clhsdb.sh line 42
```

