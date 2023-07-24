##### oe_test_postgresql-contrib_pg_qrchivecleanup:测试用例命令行参数过多

log内对应报错如下

```
+ su - postgres -c 'oid2name -t test "oid2name"'
+ grep Filenode
oid2name: too many command-line arguments (first is "oid2name")
Try "oid2name --help" for more information.
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

##### 