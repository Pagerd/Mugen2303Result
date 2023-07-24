### oe_test_ebtables:测试用例没有安装ebtables

riscv与x86报错均相同

下为报错log

```
+ ebtables --concurrent -L
oe_test_ebtables.sh: line 30: ebtables: command not found
```

测试套内环境搭建代码如下

```
function pre_test() {
    LOG_INFO "Start to prepare the test environment."
    touch /run/ebtables.lock
    LOG_INFO "End to prepare the test environment."
}

```

因此测试用例没有安装ebtables