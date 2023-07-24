#### oe_test_postgresql_vacuumdb:测试套编写错误

测试套内对应代码如下

```
    su - postgres -c "vacuumdb -z -e"
    CHECK_RESULT $?
    psql testdb -U postgres -h 127.0.0.1 -c "insert into test select generate_series(1,100000),random();"
    psql testdb -U postgres -h 127.0.0.1 -c "delete from test"
    temp1=$(du /var/lib/pgsql/data/base/$oid | awk '{printf $1}')
    su - postgres -c "vacuumdb -Z -e"
    CHECK_RESULT $?
    temp2=$(du /var/lib/pgsql/data/base/$oid | awk '{printf $1}')
    [ $temp1 -eq $temp2 ]
    CHECK_RESULT $?
```

报错为此行Z大写

```
    su - postgres -c "vacuumdb -Z -e"
```

经查阅相关文档后vacuumdb无大写Z参数

改为小写后测试用例通过