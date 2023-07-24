##### oe_test_postgresql_pg_dump_02:测试版本pg_dump指令不支持-o参数

log内对应报错如下

```
+ su - postgres -c 'pg_dump -o testdb >testfile'
pg_dump: invalid option -- 'o'
```

##### 