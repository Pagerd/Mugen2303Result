##### oe_test_postgresql-server_pg_receivewal:测试套中的正则表达式错误

log内对应报错如下

```
++ pgrep -f 'pg_receivewal -D /var/lib/pgsql/pg_receivewal -h ${NODE1_IPV4} -U sstest -w -p 5432'
pgrep: regex error: Invalid preceding regular expression
+ kill -9
kill: usage: kill [-s sigspec | -n signum | -sigspec] pid | jobspec ... or kill -l [sigspec]
+ CHECK_RESULT 2
+ actual_result=2
+ expect_result=0
......
pg_receivewal: error: FATAL:  role "sstest" does not exist
```

### 