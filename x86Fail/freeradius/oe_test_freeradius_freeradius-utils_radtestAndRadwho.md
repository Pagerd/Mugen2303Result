# oe_test_freeradius_freeradius-utils_radtestAndRadwho

x86 和 riscv 失败原因一致， radiusd.service 启动失败导致一系列错误

```
+ echo 'steve  Cleartext-Password := "testing"
       Service-Type = Framed-User,
       Framed-Protocol = PPP,
       Framed-IP-Address = 172.16.3.33,
       Framed-IP-Netmask = 255.255.255.0,
       Framed-Routing = Broadcast-Listen,
       Framed-Filter-Id = "std.ppp",
       Framed-MTU = 1500,
       Framed-Compression = Van-Jacobsen-TCP-IP
    '
oe_test_freeradius_freeradius-utils_radtestAndRadwho.sh: line 34: /etc/raddb/users: No such file or directory
+ systemctl start radiusd
Job for radiusd.service failed because the control process exited with error code.
See "systemctl status radiusd.service" and "journalctl -xeu radiusd.service" for details.


× radiusd.service - FreeRADIUS high performance RADIUS server.
     Loaded: loaded (/usr/lib/systemd/system/radiusd.service; disabled; vendor preset: disabled)
     Active: failed (Result: exit-code) since Fri 2023-07-21 04:00:23 UTC; 3s ago
    Process: 5191 ExecStartPre=/bin/chown -R radiusd.radiusd /var/run/radiusd (code=exited, status=0/SUCCESS)
    Process: 5193 ExecStartPre=/usr/sbin/radiusd -C (code=exited, status=1/FAILURE)

Jul 21 04:00:23 localhost.localdomain systemd[1]: Starting FreeRADIUS high performance RADIUS server....
Jul 21 04:00:23 localhost.localdomain systemd[1]: radiusd.service: Control process exited, code=exited, status=1/FAILURE
Jul 21 04:00:23 localhost.localdomain systemd[1]: radiusd.service: Failed with result 'exit-code'.
Jul 21 04:00:23 localhost.localdomain systemd[1]: Failed to start FreeRADIUS high performance RADIUS server..
```

