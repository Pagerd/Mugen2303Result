### oe_test_qpdf_qpdf_08:测试套算法写入测试编写错误

riscv与x86报错相同

qpdf无法使用弱密码算法写入文件

对应报错log如下

```
+ qpdf --static-aes-iv --static-id --encrypt test123 test123 128 -- ./common/infile.pdf output6.pdf
qpdf: refusing to write a file with RC4, a weak cryptographic algorithm
Please use 256-bit keys for better security.
Pass --allow-weak-crypto to enable writing insecure files.
See also https://qpdf.readthedocs.io/en/stable/weak-crypto.html
qpdf: refusing to write a file with weak crypto
```

