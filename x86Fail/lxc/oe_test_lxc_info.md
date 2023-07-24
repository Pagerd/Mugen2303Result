# oe_test_lxc_info

x86 和 riscv 失败原因一致

容器启动失败导致后续测试失败


```
+ lxc-start myEuler1
lxc-start: myEuler1: lxccontainer.c: do_lxcapi_start: 1042 Empty args detected
lxc-start: myEuler1: tools/lxc_start.c: main: 412 The container failed to start
lxc-start: myEuler1: tools/lxc_start.c: main: 415 To get more details, run the container in foreground mode
lxc-start: myEuler1: tools/lxc_start.c: main: 417 Additional information can be obtained by setting the --logfile and --logpriority options
+ CHECK_RESULT 1 0 0 'Failed to start container.'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Failed to start container.'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Failed to start container.'
+ LOG_ERROR 'Failed to start container.'
+ message='Failed to start container.'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Failed to start container.'
Wed Jun  7 11:21:12 2023 - ERROR - Failed to start container.
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_lxc_info.sh line 33'
+ message='oe_test_lxc_info.sh line 33'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lxc_info.sh line 33'
Wed Jun  7 11:21:13 2023 - ERROR - oe_test_lxc_info.sh line 33
```

