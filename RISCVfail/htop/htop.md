##### oe_test_htop_02:

测试套编写错误,htop -V测试时v为小写导致测试失败,下为log内对应报错部分

```
 htop -v
+ grep htop
htop: invalid option -- 'v'
+ CHECK_RESULT 1 0 0 'Option test -v fails'
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log='Option test -v fails'
```

下为测试套内对应的

	htop -v | grep "htop"
	CHECK_RESULT $? 0 0 "Option test -v fails"

实际测试htop版本指令时v应为大写 

```
[root@openeuler-riscv64 ~]# htop -V
htop 3.2.1
```

修改测试套内的错误后测试通过