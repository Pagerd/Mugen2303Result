### oe_test_high_nbde:没有相关的软件包

riscv与x86均为相同错误

安装时没有对应软件包

对应log如下

```
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs tang --node 2 --tempfile ''
Traceback (most recent call last):
  File "/root/mugen/libs/locallibs/rpm_manage.py", line 176, in <module>
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

