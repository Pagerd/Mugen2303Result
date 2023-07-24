#### oe_test_itstool_2.0.4:包错误

对应报错log如下

```
+ itstool -j common/IT-join-1.xml common/IT-join-1-cs.mo common/IT-join-1-de.mo
Traceback (most recent call last):
  File "/usr/bin/itstool", line 1683, in <module>
    out.write(serialized)
TypeError: write() argument must be str, not bytes
```

### 