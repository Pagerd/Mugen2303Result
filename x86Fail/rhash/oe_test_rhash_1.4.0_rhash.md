#### oe_test_rhash_1.4.0_rhash:哈希值出错

测试套内对应失败的测试方法如下

```
rhash --edonr512 test1K.data 2>&1 | grep "cd0f7ecf145c769e462cb3d1cda0a7fb5503c11b0e29e0fe9071c27e07a74f2448686a2e54619dcee8ffcbc1012f6b393faf5e40de01f76f8c75689684c161e2  test1K.data"
```

实际测试结果如下

```
[root@openeuler-riscv64 common]# rhash --edonr512 test1K.data
9052ac32582d303e8220b7b1d3b187b2b7a43239bbb708222346db056c852be989d4ffe00df31fe80789a568096a0c4ff6dabcf77419b66bc28db871b49386e2  test1K.data
```

