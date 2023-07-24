# oe_test_audit_count_number_of_event
# oe_test_audit_count_time

## 共性的问题

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包

```
+ aureport -e -i --summary
+ grep 'Event Summary Report'
oe_test_audit_count_number_of_event.sh: line 27: aureport: command not found
```

## riscv 独有的问题

riscv 镜像没有预装 service 命令

```
+ service auditd restart
oe_test_audit_count_number_of_event.sh: line 25: service: command not found
```

