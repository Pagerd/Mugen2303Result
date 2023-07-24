# oe_test_openssl_Diffie_Hellman

测试套问题， x86 和 riscv 原因一致，测试命令所给参数不正确

```
    openssl dhparam -in dhparam.pem -noout -C
    CHECK_RESULT $?
```

报错如下

```
+ openssl dhparam -in dhparam.pem -noout -C
dhparam: Unknown option: -C
dhparam: Use -help for summary.
```

