### oe_test_pesign_efisiglist：测试套没有安装efisiglist/没有安装对应软件

riscv上没有安装efisiglist就开始测试，导致命令未知

```
+ efisiglist -i ./baidu -o test -a -h 741a03a10f3de6b2eb81985d06b70f549e762d2e9a1895c5156ffc5e10ffde33 -t sha256
oe_test_pesign_efisiglist.sh: line 40: efisiglist: command not found
```

而x86没有预装unzip，因此无法解压测试文件进行测试

```
+ unzip baidu.zip
oe_test_pesign_base_02.sh: line 29: unzip: command not found
```

