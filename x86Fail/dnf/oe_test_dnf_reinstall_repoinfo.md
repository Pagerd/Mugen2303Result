# oe_test_dnf_reinstall_repoinfo

测试套问题， x86 和 riscv 原因不同

riscv 由于软件源结构不同， ``dnf`` 输出与预期不符

x86 则由于 Line 58-59 的测试很可能失败

```
    dnf update-minimal --assumeno 2>&1 | grep "Upgrading:"
    CHECK_RESULT $?
```

在这个测试中，若没有可更新的软件包，将无法 grep 到预期的字串，导致测试失败

```
# dnf update-minimal --assumeno 2>&1

Last metadata expiration check: 0:05:22 ago on Wed 19 Jul 2023 01:33:37 PM UTC.
Dependencies resolved.
Nothing to do.
Complete!
```

