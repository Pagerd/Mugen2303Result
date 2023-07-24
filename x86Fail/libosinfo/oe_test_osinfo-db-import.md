# oe_test_osinfo-db-import

测试套问题， x86 和 riscv 失败原因不同

测试套依赖 wget 命令，但是这个命令没有被显式安装，且在 x86 镜像没有被预装

```
+ wget https://releases.pagure.org/libosinfo/osinfo-db-20230308.tar.xz
oe_test_osinfo-db-import.sh: line 31: wget: command not found
```

在 riscv 上 ``osinfo-db-export`` 输出不符合预期

```
+ osinfo-db-export
+ CHECK_RESULT 0 0 0 'Failed to export data'
+ actual_result=0
+ expect_result=0
+ mode=0
+ error_log='Failed to export data'
+ exit_mode=0
+ '[' -z 0 ']'
+ '[' 0 -eq 0 ']'
+ test 0x '!=' 0x
+ return 0
+ test -e osinfo-db-20230331.tar.xz
+ CHECK_RESULT 1 0 0 'Export file does not exist'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Export file does not exist'
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n 'Export file does not exist'
+ LOG_ERROR 'Export file does not exist'
+ message='Export file does not exist'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Export file does not exist'
Fri Jun  2 09:34:04 2023 - ERROR - Export file does not exist
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_osinfo-db-import.sh line 39'
+ message='oe_test_osinfo-db-import.sh line 39'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_osinfo-db-import.sh line 39'
Fri Jun  2 09:34:05 2023 - ERROR - oe_test_osinfo-db-import.sh line 39
```
