### oe_test_yajl:缺乏对应的软件包

x86与riscv报错均相同

在安装软件时显示没有对应软件包

报错内容如下

```
+ DNF_INSTALL 'yaji yaji-devel'
+ pkgs='yaji yaji-devel'
+ node=1
+ '[' -z '' ']'
+ tmpfile=
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs 'yaji yaji-devel' --node 1 --tempfile ''
+ tmpfile2='Last metadata expiration check: 3:15:40 ago on Fri 16 Jun 2023 01:09:39 AM CST.
No match for argument: yaji
No match for argument: yaji-devel
Error: Unable to find a match: yaji yaji-devel'
+ '[' -z '' ']'
+ tmpfile='Last metadata expiration check: 3:15:40 ago on Fri 16 Jun 2023 01:09:39 AM CST.
No match for argument: yaji
No match for argument: yaji-devel
Error: Unable to find a match: yaji yaji-devel'
+ LOG_INFO 'End of environmental preparation!'
+ message='End of environmental preparation!'
```

