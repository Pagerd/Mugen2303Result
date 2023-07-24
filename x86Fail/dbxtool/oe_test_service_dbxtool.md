# oe_test_service_dbxtool

x86 和 riscv 失败原因一样

``dnf install dbxtool`` 默认会安装 fwupd 而不是 dbxtool ，导致测试失败。

```
# dnf install dbxtool

Last metadata expiration check: 0:04:00 ago on Wed 19 Jul 2023 11:56:06 AM UTC.
Dependencies resolved.
================================================================================
 Package                        Arch     Version                     Repo  Size
================================================================================
Installing:
 fwupd                          x86_64   1.8.6-5.oe2303              OS   3.3 M
Installing dependencies:
 binutils                       x86_64   2.37-14.oe2303              OS   5.4 M
 btrfs-progs                    x86_64   6.0-1.oe2303                OS   708 k
 cpp                            x86_64   10.3.1-26.oe2303            OS   9.0 M
 ......
```

不过手动指定安装 dbxtool 后测试依然无法启动 dbxtool.service ，且报错一致

```
Condition check resulted in Secure Boot DBX (blacklist) updater being skipped.
```


