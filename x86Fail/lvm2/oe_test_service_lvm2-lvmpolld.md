# oe_test_service_lvm2-lvmpolld

x86 和 riscv 错误原因一致， lvm2-lvmpolld.service 错误如下

```
+ journalctl --since '2023-06-05 17:43:42' -u lvm2-lvmpolld.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
Jun 05 17:43:42 openeuler-riscv64 systemd[1]: lvm2-lvmpolld.service: Failed with result 'exit-code'.
Jun 05 17:43:58 openeuler-riscv64 systemd[1]: lvm2-lvmpolld.service: Failed with result 'exit-code'.
+ CHECK_RESULT 0 0 1 'There is an error message for the log of lvm2-lvmpolld.service'
+ actual_result=0
+ expect_result=0
+ mode=1
+ error_log='There is an error message for the log of lvm2-lvmpolld.service'
+ exit_mode=0
+ '[' -z 0 ']'
+ '[' 1 -eq 0 ']'
+ test 0x == 0x
+ test -n 'There is an error message for the log of lvm2-lvmpolld.service'
+ LOG_ERROR 'There is an error message for the log of lvm2-lvmpolld.service'
+ message='There is an error message for the log of lvm2-lvmpolld.service'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'There is an error message for the log of lvm2-lvmpolld.service'
Mon Jun  5 17:44:08 2023 - ERROR - There is an error message for the log of lvm2-lvmpolld.service
```

