### oe_test_openssh_port:firewalld.service服务未加载

在尝试关闭firewalld.service时出错，firewalld.service服务未加载

riscv与x86报错均相同，如下

```
+ bash /root/mugen/libs/locallibs/sshcmd.sh -c '
    sed -i '\''s/#Port 22/Port 50000/g'\'' /etc/ssh/sshd_config
    systemctl restart sshd
    systemctl stop firewalld
    ' -i 10.198.114.6 -u root -p 'openEuler12#$' -t 300 -o 22
Fri Jun 16 04:14:42 2023 - WARN  - the remote user uses the default configuration.
Fri Jun 16 04:14:42 2023 - WARN  - the remote password uses the default configuration.
Fri Jun 16 04:14:43 2023 - WARN  - the connect port using the default configuration
spawn ssh -o ConnectTimeout=300 -p 22 root@10.198.114.6 
    sed -i 's/#Port 22/Port 50000/g' /etc/ssh/sshd_config
    systemctl restart sshd
    systemctl stop firewalld
    

root@10.198.114.6's password: 
Failed to stop firewalld.service: Unit firewalld.service not loaded.
```

