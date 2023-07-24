# oe_test_dnf_list_mark

测试套问题， x86 和 riscv 原因不同

riscv 由于软件源结构不同， ``dnf`` 输出与预期不符

x86 则由于 Line 42-45 两个测试很可能失败

```
    dnf list --updates | grep "Available Upgrades"
    CHECK_RESULT $?
    dnf list --upgrades | grep "Available Upgrades"
    CHECK_RESULT $?
```

在这两个测试中，若没有可更新的软件包，将无法 grep 到预期的字串，导致测试失败

```
# dnf list --updates

OS                                               36 kB/s | 3.8 kB     00:00    
everything                                       47 kB/s | 3.8 kB     00:00    
EPOL                                             32 kB/s | 3.0 kB     00:00    
debuginfo                                        25 kB/s | 3.8 kB     00:00    
source                                           43 kB/s | 3.8 kB     00:00    
update                                           35 kB/s | 3.0 kB     00:00    
update-source                                    31 kB/s | 3.0 kB     00:00


# dnf list --upgrades

Last metadata expiration check: 0:03:20 ago on Wed 19 Jul 2023 01:33:37 PM UTC.
```

