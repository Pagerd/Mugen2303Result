# oe_test_lvm2_pvchange_001

x86 和 riscv 失败原因不同

x86 失败由于 mugen 将 /dev/sr0 也作为可用的块设备参与测试，导致失败

```
+ pvcreate -y /dev/sr0
  Device open 11:0 has no path names.
  Cannot use /dev/sr0: device not found
```

riscv 失败日志如下

```
+ pvdisplay
+ grep 'PV UUID'
  PV UUID               W7KM2V-FQ8G-vFgX-o3re-xMqe-bmnf-IbUyKT
+ pvcreate -y /dev/vdb --setphysicalvolumesize 30MB
+ grep 'successfully created'
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
+ awk '{print$4}'
+ grep 30.00m
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
+ LOG_ERROR 'oe_test_lvm2_pvcreate_001.sh line 35'
+ message='oe_test_lvm2_pvcreate_001.sh line 35'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_lvm2_pvcreate_001.sh line 35'
Mon Jun  5 17:54:41 2023 - ERROR - oe_test_lvm2_pvcreate_001.sh line 35
```

