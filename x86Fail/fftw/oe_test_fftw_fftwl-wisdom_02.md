# oe_test_fftw_fftwl-wisdom_02

x86 和 riscv 错误原因一致

测试脚本如下：

```
    TMP_DIR="$(mktemp -d -t fftw.XXXXXXXXXXXX)"
    echo "(fftw-3.3.8 fftwl_wisdom #xc55000ae #xe28b9b3a #x070e76c6 #xeeae5518
(fftwl_codelet_n1_16 0 #x12345 #x22222 #x0 #x4396230b #x936694df #xa8dfdff3 #x77777777)
)" > ${TMP_DIR}/fftwl_wisdom

    fftwl-wisdom -w ${TMP_DIR}/fftwl_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwl-wisdom -w failed."
    fftwl-wisdom -w - < ${TMP_DIR}/fftwl_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwl-wisdom -w STDIN failed."
    fftwl-wisdom --wisdom-file ${TMP_DIR}/fftwl_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwl-wisdom --wisdom-file failed."
```

手动测试结果如下

```
# fftwl-wisdom -w ${TMP_DIR}/fftwl_wisdom 2>&1
fftw_wisdom: error reading wisdom from "/tmp/fftw.QfACCZyZdUSg/fftwl_wisdom"

# fftwl-wisdom -w - < ${TMP_DIR}/fftwl_wisdom 2>&1
fftw_wisdom: error reading wisdom from "-"

# fftwl-wisdom --wisdom-file ${TMP_DIR}/fftwl_wisdom 2>&1 
fftw_wisdom: error reading wisdom from "/tmp/fftw.QfACCZyZdUSg/fftwl_wisdom"
```

