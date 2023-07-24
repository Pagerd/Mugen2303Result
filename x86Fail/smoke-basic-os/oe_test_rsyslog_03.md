### oe_test_rsyslog_03:配置环境时丢失文件

riscv上在配置环境时复制文件显示不存在此文件

```
+ cp -f '/run/log/journal/*/system.journal' '/run/log/journal/*/system.journal.bak'
cp: cannot stat '/run/log/journal/*/system.journal': No such file or directory
+ cp -f /run/log/imjournal.state /run/log/imjournal.state.bak
cp: cannot stat '/run/log/imjournal.state': No such file or directory
```

同时测试时找不到对应启动项

```
+ systemctl restart rsyslog
Failed to restart rsyslog.service: Unit rsyslog.service not found.
+ CHECK_RESULT 5 0 0 'Rsyslog not started'
```

在x86上配置环境时报错有所不同

```
+ cp -f /run/log/journal/8a5455b74958430e8fcd2014bde5fc53/system.journal /run/log/journal/c78e8c10bbba4687b4aa7ab68adfb5e8/system.journal '/run/log/journal/*/system.journal.bak'
cp: target '/run/log/journal/*/system.journal.bak' is not a directory
```

同时在测试时报错的地方也有所不同

```
+ test -f /run/log/journal/8a5455b74958430e8fcd2014bde5fc53/system.journal /run/log/journal/c78e8c10bbba4687b4aa7ab68adfb5e8/system.journal
oe_test_rsyslog_03.sh: line 36: test: /run/log/journal/8a5455b74958430e8fcd2014bde5fc53/system.journal: binary operator expected
+ CHECK_RESULT 2 0 0 'Failed to find system.journal'
```

