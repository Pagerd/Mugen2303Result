# oe_test_audit_user_build_connection

## 共性的问题

测试套问题， x86 和 riscv 错误原因一致。测试套测试 audit 软件包，而测试套没有显式安装 audit 软件包， x86 和 riscv 镜像也都没有预装 audit 软件包

```
++ find / -name af_unix.conf
+ path=
+ sed -i 's/active = no/active = yes/g' ''
sed: can't read : No such file or directory
+ service auditd restart
Redirecting to /bin/systemctl restart auditd.service
Failed to restart auditd.service: Unit auditd.service not found.
```

## riscv 独有的问题

riscv 镜像没有预装 service 命令

```
+ service auditd restart
oe_test_audit_user_build_connection.sh: line 27: service: command not found
```

riscv 镜像没有预装 kernel-headers 软件包

```
+ gcc -o audit_socket audit_socket.c
In file included from /usr/include/bits/posix1_lim.h:161,
                 from /usr/include/limits.h:195,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/limits.h:195,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/syslimits.h:7,
                 from /usr/lib/gcc/riscv64-linux-gnu/10.3.1/include/limits.h:34,
                 from /usr/include/sys/param.h:26,
                 from audit_socket.c:2:
/usr/include/bits/local_lim.h:38:10: fatal error: linux/limits.h: No such file or directory
   38 | #include <linux/limits.h>
      |          ^~~~~~~~~~~~~~~~
compilation terminated.
```

