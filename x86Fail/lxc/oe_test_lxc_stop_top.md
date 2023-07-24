# oe_test_lxc_stop_top

x86 和 riscv 失败原因一致

容器启动失败导致后续测试失败

```
+ lxc-start -n myEuler1
lxc-start: myEuler1: lxccontainer.c: do_lxcapi_start: 1042 Empty args detected
lxc-start: myEuler1: tools/lxc_start.c: main: 412 The container failed to start
lxc-start: myEuler1: tools/lxc_start.c: main: 415 To get more details, run the container in foreground mode
lxc-start: myEuler1: tools/lxc_start.c: main: 417 Additional information can be obtained by setting the --logfile and --logpriority options
+ CHECK_RESULT 1 0 0 'Check lxc-start -n failed.'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Check lxc-start -n failed.'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Check lxc-start -n failed.'
+ LOG_ERROR 'Check lxc-start -n failed.'
+ message='Check lxc-start -n failed.'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Check lxc-start -n failed.'
Wed Jun  7 11:20:13 2023 - ERROR - Check lxc-start -n failed.
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_lxc_stop_top.sh line 39'
+ message='oe_test_lxc_stop_top.sh line 39'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lxc_stop_top.sh line 39'
Wed Jun  7 11:20:13 2023 - ERROR - oe_test_lxc_stop_top.sh line 39
```

