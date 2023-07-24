# oe_test_service_ipsec

x86 和 riscv 失败原因一致

```
+ sed -i 's\ExecStart=/usr/libexec/ipsec/pluto\ExecStart=/usr/libexec/ipsec/pluto --debug\g' /usr/lib/systemd/system/ipsec.service
+ systemctl daemon-reload
+ systemctl reload ipsec.service
Failed to reload ipsec.service: Job type reload is not applicable for unit ipsec.service.
```

