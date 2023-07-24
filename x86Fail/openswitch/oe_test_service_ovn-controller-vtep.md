### oe_test_service_ovn-controller-vtep:服务启动失败

x86上命令运行正常，但是测试套期望为失败

```
spawn service ovn-controller-vtep.service restart
Redirecting to /bin/systemctl restart ovn-controller-vtep.service
Failed to restart ovn-controller-vtep.service: Access denied
See system logs and 'systemctl status ovn-controller-vtep.service' for details.
send: spawn id exp4 not open
    while executing
"send "openEuler12#$\n""
+ grep -iE 'fail|error' /tmp/testlog1
Failed to restart ovn-controller-vtep.service: Access denied
+ CHECK_RESULT 0 1 0 'ovn-controller-vtep.service restart failed'
+ actual_result=0
+ expect_result=1
```

而riscv上因为测试命令失败所以大部分均通过，最后没有service指令导致失败

```
spawn service ovn-controller-vtep.service start
couldn't execute "service": no such file or directory
    while executing
"spawn service ovn-controller-vtep.service start"
+ grep -iE 'fail|error' /tmp/testlog3
+ CHECK_RESULT 1 1 0 'ovn-controller-vtep.service start failed'
+ actual_result=1
+ expect_result=1
+ mode=0
+ error_log='ovn-controller-vtep.service start failed'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 1x
+ return 0
+ su - openvswitch_ovn -c 'service ovn-controller-vtep.service status'
+ grep 'Active: active (running)'
-bash: line 1: service: command not found
+ CHECK_RESULT 1 0 0 'ovn-controller-vtep.service start failed'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='ovn-controller-vtep.service start failed'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'ovn-controller-vtep.service start failed'
+ LOG_ERROR 'ovn-controller-vtep.service start failed'
+ message='ovn-controller-vtep.service start failed'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'ovn-controller-vtep.service start failed'
Wed Apr 26 14:40:49 2023 - ERROR - ovn-controller-vtep.service start failed
```

