### oe_test_hdparm:没有进行环境搭建就开始测试

mugen与riscv报错均相同

下为报错部分log

```
+ hdparm -h
+ grep -i Usage
oe_test_hdparm.sh: line 27: hdparm: command not found
+ CHECK_RESULT 1 0 0 'hdparm -h fail'
```

检查测试用例编写时发现并无环境搭建函数

```
source "$OET_PATH/libs/locallibs/common_lib.sh"


function run_test() {
    LOG_INFO "Start testing..."
    lsblk >> lsblk.txt
```

