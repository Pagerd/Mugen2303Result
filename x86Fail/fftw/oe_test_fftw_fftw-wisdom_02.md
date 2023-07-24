# oe_test_fftw_fftw-wisdom_02

x86 和 riscv 错误原因一致

测试脚本如下：

```
    TMP_DIR="$(mktemp -d -t fftw.XXXXXXXXXXXX)"
    echo "(fftw-3.3.8 fftw_wisdom #x4be12fff #x7b2df9b2 #xa5975329 #x385b0041
(fftw_codelet_n1_16 0 #x12345 #x22222 #x0 #x4396230b #x936694df #xa8dfdff3 #x77777777)
)" > ${TMP_DIR}/fftw_wisdom

    fftw-wisdom -w ${TMP_DIR}/fftw_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftw-wisdom -w failed."
    fftw-wisdom -w - < ${TMP_DIR}/fftw_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftw-wisdom -w STDIN failed."
    fftw-wisdom --wisdom-file ${TMP_DIR}/fftw_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftw-wisdom --wisdom-file failed."
```

手动测试输出

```
# fftw-wisdom -w ${TMP_DIR}/fftw_wisdom 2>&1
fftw_wisdom: error reading wisdom from "/tmp/fftw.4QkXPzqmocOi/fftw_wisdom"

# fftw-wisdom -w - < ${TMP_DIR}/fftw_wisdom 2>&1
fftw_wisdom: error reading wisdom from "-"

# fftw-wisdom --wisdom-file ${TMP_DIR}/fftw_wisdom 2>&1
fftw_wisdom: error reading wisdom from "/tmp/fftw.4QkXPzqmocOi/fftw_wisdom"
```

