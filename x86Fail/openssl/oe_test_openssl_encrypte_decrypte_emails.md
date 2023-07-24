# oe_test_openssl_encrypte_decrypte_emails

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 28-31 如下所示

```
    openssl genrsa -out rsakey.pem
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' rsakey.pem
    CHECK_RESULT $?
```

grep 参数和实际不符，导致测试失败。

