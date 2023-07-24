##### oe_test_postgresql-contrib_pg_waldump:无法解析起始 WAL 位置“-n”

log内对应报错如下

```
+ su - postgres -c 'pg_waldump 000000010000000000000001 -f -s  -n 3'
+ grep rmgr
pg_waldump: error: could not parse start WAL location "-n"
Try "pg_waldump --help" for more information.
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
```

##### 