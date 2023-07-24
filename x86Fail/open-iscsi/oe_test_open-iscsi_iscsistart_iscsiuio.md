### oe_test_open-iscsi_iscsistart_iscsiuio:软件包安装出错

riscv与x86均为相同错误

下为对应log

```
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs 'targetcli net-tools' --node 2 --tempfile /tmp/tmpudypg5us
Traceback (most recent call last):
  File "/root/mugen/libs/locallibs/rpm_manage.py", line 168, in <module>
    exitcode, output = rpm_install(args.pkgs, args.node, args.tempfile)
  File "/root/mugen/libs/locallibs/rpm_manage.py", line 66, in rpm_install
    conn = ssh_cmd.pssh_conn(
  File "/root/mugen/libs/locallibs/ssh_cmd.py", line 53, in pssh_conn
    conn.connect(ip, port, user, password, timeout=timeout)
  File "/usr/lib/python3.10/site-packages/paramiko/client.py", line 340, in connect
    to_try = list(self._families_and_addresses(hostname, port))
  File "/usr/lib/python3.10/site-packages/paramiko/client.py", line 203, in _families_and_addresses
    addrinfos = socket.getaddrinfo(
  File "/usr/lib64/python3.10/socket.py", line 955, in getaddrinfo
    for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
socket.gaierror: [Errno -2] Name or service not known
```

