# oe_test_server_openssh_verifykey

x86 和 riscv 错误原因一致，测试套问题

测试依赖 ``setsebool`` 命令，该命令依赖 policycoreutils 软件包，该软件包在 x86 和 riscv 镜像中均没有预装

```
+ setsebool -P use_nfs_home_dirs 1
oe_test_server_openssh_verifykey.sh: line 32: setsebool: command not found
```

导致后续命令出错，测试失败

```
+ bash /root/mugen/libs/locallibs/sshcmd.sh -c ls -i 10.198.114.1 -u root -p 'openEuler12#$' -t 300 -o 22
Mon May  8 09:07:12 2023 - WARN  - the remote user uses the default configuration.
Mon May  8 09:07:13 2023 - WARN  - the remote password uses the default configuration.
Mon May  8 09:07:13 2023 - WARN  - the connect port using the default configuration
spawn ssh -o ConnectTimeout=300 -p 22 root@10.198.114.1 ls

The authenticity of host '10.198.114.1 (10.198.114.1)' can't be established.
ED25519 key fingerprint is SHA256:M6IZ/zy3MxMo6/o/fy+aY4RQYnH9M5BZVPilD5Busik.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:1: 10.198.114.2
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.198.114.1' (ED25519) to the list of known hosts.


Authorized users only. All activities may be monitored and reported.
root@10.198.114.1: Permission denied (publickey,gssapi-with-mic).

send: spawn id exp4 not open
    while executing
"send "openEuler12#$\r""
    invoked from within
"expect {
            "Are you sure you want to continue connecting*"
            {
                send "yes\r"
                expect "*\[P|p]assword..."
+ ret=1
```

