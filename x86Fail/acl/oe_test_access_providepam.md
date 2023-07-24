# oe_test_access_providepam

测试测得 /usr/lib64/security/pam_systemd.so 文件不存在，该文件由 systemd-pam 软件包提供，该软件包在 x86 和 riscv 镜像均没有预装

```
+ test -e /usr/lib64/security/pam_systemd.so
+ CHECK_RESULT 1 0 0 'pam_systemd.so not exist'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='pam_systemd.so not exist'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'pam_systemd.so not exist'
+ LOG_ERROR 'pam_systemd.so not exist'
+ message='pam_systemd.so not exist'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'pam_systemd.so not exist'
Thu May 25 16:47:20 2023 - ERROR - pam_systemd.so not exist
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_access_providepam.sh line 27'
+ message='oe_test_access_providepam.sh line 27'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_access_providepam.sh line 27'
Thu May 25 16:47:20 2023 - ERROR - oe_test_access_providepam.sh line 27
```

