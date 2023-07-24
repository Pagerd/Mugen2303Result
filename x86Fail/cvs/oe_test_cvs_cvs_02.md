### oe_test_cvs_cvs_02:测试用例没有权限执行操作

 riscv与x86报错均相同

对应报错log为

```
+ su cvsroot -c 'cvs init'
cvs init: cannot open /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT/config: Permission denied
cvs [init aborted]: cannot make directory /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir: Permission denied
+ CHECK_RESULT 1 0 0 'test cvs init failed'
```

