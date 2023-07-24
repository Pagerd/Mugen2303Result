# oe_test_audit_ausearch

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包，不 fail 才怪

```
+ auditctl -w /home/uos1/testfile -p rwxa -k testfile_audit
oe_test_audit_ausearch.sh: line 26: auditctl: command not found

+ ausearch --format csv
oe_test_audit_ausearch.sh: line 32: ausearch: command not found
```

