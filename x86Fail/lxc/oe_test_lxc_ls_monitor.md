# oe_test_lxc_ls_monitor

x86 和 riscv 失败原因一致

失败日志

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
Fri Jun  2 14:50:17 2023 - ERROR - Check lxc-start -n failed.
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_lxc_ls_monitor.sh line 43'
+ message='oe_test_lxc_ls_monitor.sh line 43'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lxc_ls_monitor.sh line 43'
Fri Jun  2 14:50:18 2023 - ERROR - oe_test_lxc_ls_monitor.sh line 43
+ '[' 0 -eq 1 ']'
+ return 0
+ lxc-ls --running
+ grep myEuler1
+ CHECK_RESULT 1 0 0 'Check lxc-ls --running failed.'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Check lxc-ls --running failed.'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Check lxc-ls --running failed.'
+ LOG_ERROR 'Check lxc-ls --running failed.'
+ message='Check lxc-ls --running failed.'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Check lxc-ls --running failed.'
Fri Jun  2 14:50:19 2023 - ERROR - Check lxc-ls --running failed.
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_lxc_ls_monitor.sh line 45'
+ message='oe_test_lxc_ls_monitor.sh line 45'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lxc_ls_monitor.sh line 45'
Fri Jun  2 14:50:19 2023 - ERROR - oe_test_lxc_ls_monitor.sh line 45
```

