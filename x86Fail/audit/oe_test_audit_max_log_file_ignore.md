# oe_test_audit_max_log_file_ignore

## 共性的问题

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包

```
../common/comlib.sh: line 30: auditctl: command not found
++ ls -i /var/log/audit/audit.log
++ awk '-F ' '{print $1}'
ls: cannot access '/var/log/audit/audit.log': No such file or directory
+ new=
++ du -ks /var/log/audit/audit.log
++ awk '{print $1}'
du: cannot access '/var/log/audit/audit.log': No such file or directory
+ log_size=
+ test '' -gt 1024
oe_test_audit_max_log_file_ignore.sh: line 38: test: : integer expression expected
```

## riscv 独有的问题

riscv 镜像没有预装 service 命令

```
+ service auditd restart
Redirecting to /bin/systemctl restart auditd.service
```

