# oe_test_crontabs

x86 和 riscv 错误完全一致

```
+ crontab -u root -l -s
Cannot obtain SELinux process context
+ CHECK_RESULT 1 0 0 'Failed option: -s'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Failed option: -s'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Failed option: -s'
+ LOG_ERROR 'Failed option: -s'
+ message='Failed option: -s'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Failed option: -s'
Thu May 25 16:39:01 2023 - ERROR - Failed option: -s
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_crontabs.sh line 51'
+ message='oe_test_crontabs.sh line 51'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_crontabs.sh line 51'
Thu May 25 16:39:02 2023 - ERROR - oe_test_crontabs.sh line 51
```

