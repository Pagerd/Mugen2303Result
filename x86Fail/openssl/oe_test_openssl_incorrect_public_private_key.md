# oe_test_openssl_incorrect_public_private_key

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 24-27 Line 33-34 Line 40-41 如下所示

```
    openssl genrsa -out rsakey.pem -passout pass:123123 2048
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' rsakey.pem
    CHECK_RESULT $?

    openssl rsautl -encrypt -pubin -inkey error_rsakey-pub.pem -in word -out wordencp2 2>&1 | grep "unable to load Public Key"
    CHECK_RESULT $? 0 0 "Incorrect public key succeeded in encrypting the file"

    openssl rsautl -decrypt -inkey error_rsakey.pem -in wordencp2 -out word_replain2 2>&1 | grep 'unable to load Private Key'
    CHECK_RESULT $? 0 0 "The wrong private key successfully decrypted the file"
```

grep 参数和实际不符，导致测试失败。

