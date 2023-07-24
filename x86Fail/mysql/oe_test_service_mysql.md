# oe_test_service_mysql

测试套问题， x86 和 riscv 失败原因一致

测试套测试 mysql.service 但是没有软件包提供该 daemon

```
+ systemctl status mysql.service
+ grep 'Active: active'
Unit mysql.service could not be found.
```

dnf 无法找到提供 mysql.service 的软件包

```
# dnf provides */mysql.service
Last metadata expiration check: 0:50:43 ago on Fri 21 Jul 2023 12:00:00 AM CST.
Error: No matches found. If searching for a file, try specifying the full path or using a wildcard prefix ("*/") at the beginning.
```

