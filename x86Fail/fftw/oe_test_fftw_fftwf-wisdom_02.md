# oe_test_fftw_fftwf-wisdom_02

x86 和 riscv 错误原因一致

测试脚本如下

```
    TMP_DIR="$(mktemp -d -t fftw.XXXXXXXXXXXX)"
    echo "(fftw-3.3.8 fftwf_wisdom #xca4daf64 #xc8f59ea6 #x586875c9 #x14018994
(fftwf_codelet_n1_16 0 #x12345 #x22222 #x0 #x4396230b #x936694df #xa8dfdff3 #x77777777)
)" > ${TMP_DIR}/fftwf_wisdom

    fftwf-wisdom -w ${TMP_DIR}/fftwf_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwf-wisdom -w failed."
    fftwf-wisdom -w - < ${TMP_DIR}/fftwf_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwf-wisdom -w STDIN failed."
    fftwf-wisdom --wisdom-file ${TMP_DIR}/fftwf_wisdom 2>&1 | grep -q "#x12345"
    CHECK_RESULT $? 0 0 "Check fftwf-wisdom --wisdom-file failed."
```

手动测试结果

```
# fftwf-wisdom -w ${TMP_DIR}/fftwf_wisdom 2>&1
fftw_wisdom: error reading wisdom from "/tmp/fftw.uNxOahLRQlQI/fftwf_wisdom"

# fftwf-wisdom -w - < ${TMP_DIR}/fftwf_wisdom
fftw_wisdom: error reading wisdom from "-"

# fftwf-wisdom --wisdom-file ${TMP_DIR}/fftwf_wisdom 2>&1
fftw_wisdom: error reading wisdom from "/tmp/fftw.uNxOahLRQlQI/fftwf_wisdom"
```

