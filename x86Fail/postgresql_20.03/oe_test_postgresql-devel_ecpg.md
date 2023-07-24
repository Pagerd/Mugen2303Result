##### oe_test_postgresql-devel_ecpg:测试版本无ecpg命令支持

log内对应报错如下

```
+ su - postgres -c 'ecpg -c test.sqc'
-bash: line 1: ecpg: command not found
+ CHECK_RESULT 127
+ actual_result=127
+ expect_result=0
```

##### 