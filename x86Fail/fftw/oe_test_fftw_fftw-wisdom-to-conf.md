# oe_test_fftw_fftw-wisdom-to-conf

x86 和 riscv 一致，测试脚本如下

```
    echo "(fftw-3.3.8 fftw_wisdom #x4be12fff #x7b2df9b2 #xa5975329 #x385b0041
    (fftw_codelet_n1_16 0 #x12345 #x22222 #x0 #x4396230b #x936694df #xa8dfdff3 #x77777777)
    )" > ./tmp/wisdom

    fftw-wisdom-to-conf < ./tmp/wisdom | grep -q "fftw_configure_planner"
    CHECK_RESULT $? 0 0 "Check fftw-wisdom-to-conf output failed."
```

错误如下：

```
+ fftw-wisdom-to-conf
+ grep -q fftw_configure_planner
fftw-wisdom-to-conf: invalid wisdom
+ CHECK_RESULT 1 0 0 'Check fftw-wisdom-to-conf output failed.'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Check fftw-wisdom-to-conf output failed.'
```

