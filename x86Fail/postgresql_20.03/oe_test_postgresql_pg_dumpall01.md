##### oe_test_postgresql_pg_dumpall01:测试版本pg_dumpall指令不支持-o参数

log内对应报错如下

```
+ su - postgres -c 'pg_dumpall -o > /var/lib/pgsql/test.sql'
pg_dumpall: invalid option -- 'o'
```

##### 