### oe_test_service_samba：服务加载失败

riscv对应报错为

```
spawn samba-tool domain provision --use-rfc2307 --interactive --function-level=2008_R2
Traceback (most recent call last):
  File "/usr/bin/samba-tool", line 33, in <module>
    from samba.netcmd.main import cmd_sambatool
  File "/usr/lib64/python3.10/site-packages/samba/__init__.py", line 29, in <module>
    import samba.param
ImportError: libserver-role-samba4.so: cannot open shared object file: No such file or directory
expect: spawn id exp3 not open
    while executing
"expect eof"
+ mv /etc/krb5.conf /etc/krb5.bak
```

x86对应报错为

```
++ hostname
oe_test_service_samba.sh: line 24: hostname: command not found
+ host_name=
+ hostname OE-TESTD
oe_test_service_samba.sh: line 25: hostname: command not found
+ echo '127.0.0.1 TESTAD.LOCAL'
```

