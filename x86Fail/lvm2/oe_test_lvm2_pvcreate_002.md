# oe_test_lvm2_pvcreate_002

x86 和 riscv 失败原因不同

x86 失败由于 mugen 将 /dev/sr0 也作为可用的块设备参与测试，导致失败

```
+ pvcreate /dev/sr0 -y --setphysicalvolumesize 50MB
+ grep 'successfully created'
  Device open 11:0 has no path names.
  Cannot use /dev/sr0: device not found
```

riscv 失败日志如下

```
+ pvcreate /dev/vdb -y --setphysicalvolumesize 50MB
  WARNING: Faking size of PV /dev/vdb. Don't write outside real device.
  Physical volume "/dev/vdb" successfully created.
+ CHECK_RESULT 0
+ actual_result=0
+ expect_result=0
+ mode=0
+ error_log=
+ exit_mode=0
+ '[' -z 0 ']'
+ '[' 0 -eq 0 ']'
+ test 0x '!=' 0x
+ return 0
+ pvs
+ sed -n 3p
+ grep 50.00m
+ awk '{print$4}'
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
+ LOG_ERROR 'oe_test_lvm2_pvcreate_002.sh line 35'
+ message='oe_test_lvm2_pvcreate_002.sh line 35'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lvm2_pvcreate_002.sh line 35'
Mon Jun  5 17:53:11 2023 - ERROR - oe_test_lvm2_pvcreate_002.sh line 35
```

