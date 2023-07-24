# oe_test_openssl_file_signature_verification

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 22-25 和 Line 34-37 如下所示

```
    LOG_INFO "Start to run test."
    openssl dsaparam -noout -out dsakey.pem -genkey 2048
    CHECK_RESULT $?
    grep 'BEGIN DSA PRIVATE KEY' dsakey.pem

    openssl genrsa -out rsakey.pem
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' rsakey.pem
    CHECK_RESULT $?
```

grep 参数和实际不符，导致测试失败。

