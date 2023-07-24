# oe_test_openssl_create_CA_applying_certificate

测试套问题，x86 和 riscv 错误原因一致

错误来自 Line 33-36

```
    openssl genrsa -out $CA_Path/private/cakey.pem 2048
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' $CA_Path/private/cakey.pem
    CHECK_RESULT $?
```

grep 所示字串和实际不符

