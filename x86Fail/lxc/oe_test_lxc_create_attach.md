# oe_test_lxc_create_attach

x86 和 riscv 失败原因一致

失败日志

```
+ lxc-start myEuler1
lxc-start: myEuler1: lxccontainer.c: do_lxcapi_start: 1042 Empty args detected
lxc-start: myEuler1: tools/lxc_start.c: main: 412 The container failed to start
lxc-start: myEuler1: tools/lxc_start.c: main: 415 To get more details, run the container in foreground mode
lxc-start: myEuler1: tools/lxc_start.c: main: 417 Additional information can be obtained by setting the --logfile and --logpriority options
+ expect -c '
    log_file testlog2
    spawn lxc-attach -n myEuler1
    expect "#"
    send "exit\r"
    expect eof
'
spawn lxc-attach -n myEuler1
lxc-attach: myEuler1: attach.c: lxc_attach: 1314 Failed to get init pid
myEuler1:tools/lxc_attach.c:main:731 starting container process caused "Internal error, failed to call attach"send: spawn id exp4 not open
    while executing
"send "exit\r""
+ grep 'while executing' testlog2
    while executing
+ CHECK_RESULT 0 1 0 'Check lxc-attach -n failed.'
+ actual_result=0
+ expect_result=1
+ mode=0
+ error_log='Check lxc-attach -n failed.'
+ exit_mode=0
+ '[' -z 0 ']'
+ '[' 0 -eq 0 ']'
+ test 0x '!=' 1x
+ test -n 'Check lxc-attach -n failed.'
+ LOG_ERROR 'Check lxc-attach -n failed.'
+ message='Check lxc-attach -n failed.'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Check lxc-attach -n failed.'
Wed Jun  7 11:10:37 2023 - ERROR - Check lxc-attach -n failed.
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_lxc_create_attach.sh line 53'
+ message='oe_test_lxc_create_attach.sh line 53'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lxc_create_attach.sh line 53'
Wed Jun  7 11:10:37 2023 - ERROR - oe_test_lxc_create_attach.sh line 53
```

