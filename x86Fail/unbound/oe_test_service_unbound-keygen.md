### oe_test_service_unbound-keygen：service无法启动

riscv中没有对应服务项

```
× unbound-keygen.service
     Loaded: not-found (Reason: Unit unbound-keygen.service not found.)
     Active: failed (Result: exit-code) since Thu 2023-04-27 04:48:46 CST; 42s ago
  Condition: start condition failed at Thu 2023-04-27 04:49:06 CST; 22s ago
   Main PID: 1576 (code=exited, status=203/EXEC)
```

x86中，缺乏对应文件导致测试失败

```
May 05 05:41:00 localhost.localdomain unbound-control-setup[4676]: Setup success. Certificates created. Enable in unbound.conf file to use
May 05 05:41:00 localhost.localdomain systemd[4688]: unbound-keygen.service: Failed to locate executable /sbin/restorecon: No such file or directory
░░ Subject: Process /sbin/restorecon could not be executed
░░ Defined-By: systemd
░░ Support: https://lists.freedesktop.org/mailman/listinfo/systemd-devel
░░ 
░░ The process /sbin/restorecon could not be executed and failed.
░░ 
░░ The error number returned by this process is ERRNO.
May 05 05:41:00 localhost.localdomain systemd[4688]: unbound-keygen.service: Failed at step EXEC spawning /sbin/restorecon: No such file or directory
░░ Subject: Process /sbin/restorecon could not be executed
░░ Defined-By: systemd
░░ Support: https://lists.freedesktop.org/mailman/listinfo/systemd-devel
░░ 
░░ The process /sbin/restorecon could not be executed and failed.
░░ 
░░ The error number returned by this process is ERRNO.
May 05 05:41:00 localhost.localdomain systemd[1]: unbound-keygen.service: Main process exited, code=exited, status=203/EXEC
░░ Subject: Unit process exited
░░ Defined-By: systemd
░░ Support: https://lists.freedesktop.org/mailman/listinfo/systemd-devel
░░ 
░░ An ExecStart= process belonging to unit unbound-keygen.service has exited.
```

