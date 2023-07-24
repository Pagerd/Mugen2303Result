# oe_test_service_netconsole

x86 和 riscv 失败原因一致

```
+ journalctl --since '2023-05-27 01:04:36' -u netconsole.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
May 27 01:04:37 openeuler-riscv64 systemd[1]: netconsole.service: Main process exited, code=exited, status=1/FAILURE
May 27 01:04:37 openeuler-riscv64 systemd[1]: netconsole.service: Failed with result 'exit-code'.
May 27 01:04:37 openeuler-riscv64 systemd[1]: Failed to start Initializes network console logging of kernel messages.
May 27 01:05:00 openeuler-riscv64 systemd[1]: netconsole.service: Main process exited, code=exited, status=1/FAILURE
May 27 01:05:00 openeuler-riscv64 systemd[1]: netconsole.service: Failed with result 'exit-code'.
May 27 01:05:00 openeuler-riscv64 systemd[1]: Failed to start Initializes network console logging of kernel messages.
+ CHECK_RESULT 0 0 1 'There is an error message for the log of netconsole.service'
```

