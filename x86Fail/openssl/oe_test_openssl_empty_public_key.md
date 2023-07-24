# oe_test_openssl_empty_public_key

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 24-27 如下所示

```
    openssl genrsa -out rsakey.pem -passout pass:123123 2048
    CHECK_RESULT $?
    grep 'BEGIN RSA PRIVATE KEY' rsakey.pem
    CHECK_RESULT $?
```

grep 参数和实际不符，导致测试失败。

其他错误

```
+ openssl rsautl -encrypt -pubin -inkey rsakey1-pub.pem -in word -out wordencp1
+ grep 'unable to load Public Key'
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ exit_mode=0
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_openssl_empty_public_key.sh line 31'
+ message='oe_test_openssl_empty_public_key.sh line 31'
```

