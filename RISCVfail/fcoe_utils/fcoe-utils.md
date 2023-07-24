##### oe_test_service_fcoe:

fcoe启动失败,log内对应报错内容

```
+ test_restart fcoe.service
+ service=fcoe.service
+ systemctl restart fcoe.service
Job for fcoe.service failed because the control process exited with error code.
See "systemctl status fcoe.service" and "journalctl -xeu fcoe.service" for details.
```

在本地进行systemctl status之后显示的内容

```
× fcoe.service - Open-FCoE initiator daemon
     Loaded: loaded (/usr/lib/systemd/system/fcoe.service; disabled; vendor pre>
     Active: failed (Result: exit-code) since Fri 2023-06-16 18:22:31 CST; 1min>
    Process: 473 ExecStartPre=/sbin/modprobe -qa $SUPPORTED_DRIVERS (code=exite>

Jun 16 18:22:31 openeuler-riscv64 systemd[1]: Starting Open-FCoE initiator daem>
Jun 16 18:22:31 openeuler-riscv64 systemd[1]: fcoe.service: Control process exi>
Jun 16 18:22:31 openeuler-riscv64 systemd[1]: fcoe.service: Failed with result >
Jun 16 18:22:31 openeuler-riscv64 systemd[1]: Failed to start Open-FCoE initiat>


```

### 