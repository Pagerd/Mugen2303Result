### oe_test_openssh_port:SELinux 策略不受管理或无法访问存储。

在尝试使用semanage port --delete命令时出错

riscv与x86报错均相同，如下

```
+ semanage port --delete -t ssh_port_t -p tcp 36
ValueError: SELinux policy is not managed or store cannot be accessed.
```

同时测试用例的部分命令也不支持

riscv与x86报错均相同，如下

```
+ firewall-cmd --remove-port 36/tcp
oe_test_sec_ssh.sh: line 36: firewall-cmd: command not found
+ firewall-cmd --add-port 36/tcp
oe_test_sec_ssh.sh: line 37: firewall-cmd: command not found
```

