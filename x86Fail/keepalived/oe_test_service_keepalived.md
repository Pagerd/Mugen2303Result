# oe_test_service_keepalived

测试套问题， x86 和 riscv 失败原因一致

测试套 Line 27-44 如下

```
    echo "global_defs {
   notification_email {
       root@localhost
   }
   smtp_server 127.0.0.1
   router_id N1
}
vrrp_instance VI_1 {
    state MASTER
    interface ${eth_name}
    virtual_router_id 51
    priority 100
    advert_int 1
    authentication {
        auth_type PASS
        auth_pass 1111
    }
}" >>/etc/keepalived/keepalived.conf
```

其中 ``${eth_name}`` 变量没有声明直接使用，导致该变量为空值导致测试失败

