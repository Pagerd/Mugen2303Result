### oe_test_rdate：参数测试失败

riscv与x86报错均相同

对应报错log如下

```
+ rdate -p time.nist.gov
+ grep time.nist.gov
+ [[ 1 -eq 0 ]]
+ [[ 10 == 10 ]]
+ CHECK_RESULT 0 0 1 'Failed option: -p'
+ actual_result=0
+ expect_result=0
+ mode=1
+ error_log='Failed option: -p'
```

