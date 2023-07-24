# oe_test_openssl_generate_key_pair

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 22-25 如下所示

```
    LOG_INFO "Start to run test."
    openssl genrsa -out server.pri.1024
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' server.pri.1024
```

grep 参数和实际不符，导致测试失败。

