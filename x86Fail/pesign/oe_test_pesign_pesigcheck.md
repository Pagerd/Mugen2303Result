### oe_test_pesign_pesigcheck：无效标志/没有安装对应软件

riscv在使用authvar时候报了错

```
+ authvar -i ./test -d ./baidu
authvar: invalid flags: import 
+ CHECK_RESULT 1 0 0 'Check authvar -i -d failed'
```

而x86没有预装unzip，因此无法解压测试文件进行测试

```
+ unzip baidu.zip
oe_test_pesign_base_02.sh: line 29: unzip: command not found
```

