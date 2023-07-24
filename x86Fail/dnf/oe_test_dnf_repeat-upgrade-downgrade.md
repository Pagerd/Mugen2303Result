# oe_test_dnf_repeat-upgrade-downgrade

测试套问题， x86 和 riscv 原因不同

riscv 由于软件源结构不同， ``dnf`` 输出与预期不符

x86 则由于 Line 25-34

```
    if dnf repolist | grep update; then
        dnf list --available --repo=update | grep "arch\|x86_64" | awk '{print $1}' | awk -F . 'OFS="."{$NF="";print}' | awk '{print substr($0, 1, length($0)-1)}' >update_pkg_list
        update_pkg_name=$(shuf -n1 update_pkg_list)
        if ! dnf list installed | grep $update_pkg_name; then
            dnf install -y $update_pkg_name | tee install_log
            update_pkg_name=$(grep update install_log | awk '{print $1}')
            dnf -y downgrade $update_pkg_name
        fi
    fi
```

在这个测试中，若没有可更新的软件包， ``update_pkg_list`` 将为空，导致测试失败

