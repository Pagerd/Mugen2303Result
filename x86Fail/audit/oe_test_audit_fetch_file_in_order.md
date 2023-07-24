# oe_test_audit_fetch_file_in_order

## 共性的问题

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包

```
+ service auditd restart
Redirecting to /bin/systemctl restart auditd.service
Failed to restart auditd.service: Unit auditd.service not found.

+ auditctl -D
oe_test_audit_fetch_file_in_order.sh: line 31: auditctl: command not found

+ cp -raf /usr/share/doc/audit-help/rules/30-ospp-v42.rules /etc/audit/rules.d
cp: cannot create regular file '/etc/audit/rules.d': No such file or directory
+ cp -raf /usr/share/doc/audit-help/rules/10-base-config.rules /etc/audit/rules.d
cp: cannot create regular file '/etc/audit/rules.d': No such file or directory

+ augenrules --load
oe_test_audit_fetch_file_in_order.sh: line 36: augenrules: command not found

+ auditctl -l
oe_test_audit_fetch_file_in_order.sh: line 38: auditctl: command not found
```

## riscv 独有的问题

riscv 镜像没有预装 service 命令

```
+ service auditd restart
oe_test_audit_fetch_file_in_order.sh: line 30: service: command not found
```

