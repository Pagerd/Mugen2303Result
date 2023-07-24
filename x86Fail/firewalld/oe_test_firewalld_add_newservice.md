# oe_test_firewalld_add_newservice

测试套问题，x86 和 riscv 失败原因一致，测试依赖 firewalld 软件包，但是测试用例没有显式安装之， x86 和 riscv 镜像也没有预装它

其他 firewalld 测试用例错误同理

```
+ sudo firewall-cmd --new-service=example_service --permanent
+ grep success
sudo: firewall-cmd: command not found

+ systemctl status firewalld.service
+ grep 'Active: active'
Unit firewalld.service could not be found.
```

