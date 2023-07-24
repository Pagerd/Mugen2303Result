# oe_test_audit_available_disk_space
# oe_test_audit_event_log

## 共性的问题

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包

```
+ sed -i 's/log_file = \/var\/log\/audit\/audit.log/log_file = \/tmp\/log\/audit\/audit.log/g' /etc/audit/auditd.conf
sed: can't read /etc/audit/auditd.conf: No such file or directory
+ sed -i 's/max_log_file_action = ROTATE/max_log_file_action = KEEP_LOGS/g' /etc/audit/auditd.conf
sed: can't read /etc/audit/auditd.conf: No such file or directory
+ service auditd restart
Redirecting to /bin/systemctl restart auditd.service
Failed to restart auditd.service: Unit auditd.service not found.

+ auditctl -w /tmp/available_disk_space -p rwxa -k available_disk_space
../common/comlib.sh: line 35: auditctl: command not found

+ ausearch -k available_disk_space -ts 13:51:28 -te 13:51:28
../common/comlib.sh: line 44: ausearch: command not found
```

## riscv 独有的问题

riscv 镜像没有预装 service 命令

```
+ service auditd restart
oe_test_audit_available_disk_space.sh: line 28: service: command not found
```

