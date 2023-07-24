# oe_test_service_ninfod

x86 和 riscv 失败原因一致，软件包 iputils-ninfod 不存在，无法安装

```
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs iputils-ninfod --node 1 --tempfile ''
+ tmpfile2='Last metadata expiration check: 2:09:50 ago on Thu 25 May 2023 02:48:18 PM CST.
No match for argument: iputils-ninfod
Error: Unable to find a match: iputils-ninfod'
+ '[' -z '' ']'
+ tmpfile='Last metadata expiration check: 2:09:50 ago on Thu 25 May 2023 02:48:18 PM CST.
No match for argument: iputils-ninfod
Error: Unable to find a match: iputils-ninfod'
```

