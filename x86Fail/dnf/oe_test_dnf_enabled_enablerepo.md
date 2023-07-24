# oe_test_dnf_enabled_enablerepo

测试套问题， riscv 上主要问题在于与 x86 和 aarch64 的软件源结构不同，故无法使用同样的测试套进行测试

x86 上测试脚本 Line 39-42 如下

```
    sed -i "${line1}c enabled=0" /etc/yum.repos.d/*.repo
    sed -i "${line2}c enabled=0" /etc/yum.repos.d/*.repo
    dnf repolist | grep "OS\|everything"
    CHECK_RESULT $?
```

Line 39-40 将 OS 和 everything 禁用后， Line 41 测试语句预期结果应该不为 0 ，但是测试脚本中 Line 42 预期结果为 0 。

