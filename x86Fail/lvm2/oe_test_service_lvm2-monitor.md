# oe_test_service_lvm2-monitor

x86 和 riscv 错误原因一致， lvm2-monitor.service 错误如下

```
× lvm2-monitor.service - Monitoring of LVM2 mirrors, snapshots etc. using dmeventd or progress polling
     Loaded: loaded (/usr/lib/systemd/system/lvm2-monitor.service; bad; vendor preset: enabled)
     Active: failed (Result: exit-code) since Mon 2023-06-05 17:44:54 CST; 7s ago
       Docs: man:dmeventd(8)
             man:lvcreate(8)
             man:lvchange(8)
             man:vgchange(8)
    Process: 1217 ExecStart=/usr/sbin/lvm vgchange --monitor y (code=exited, status=203/EXEC)
   Main PID: 1217 (code=exited, status=203/EXEC)

Jun 05 17:44:54 openeuler-riscv64 systemd[1]: Starting Monitoring of LVM2 mirrors, snapshots etc. using dmeventd or progress polling...
Jun 05 17:44:54 openeuler-riscv64 systemd[1]: lvm2-monitor.service: Main process exited, code=exited, status=203/EXEC
Jun 05 17:44:54 openeuler-riscv64 systemd[1]: lvm2-monitor.service: Failed with result 'exit-code'.
Jun 05 17:44:54 openeuler-riscv64 systemd[1]: Failed to start Monitoring of LVM2 mirrors, snapshots etc. using dmeventd or progress polling.
```

