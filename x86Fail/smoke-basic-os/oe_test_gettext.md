### oe_test_gettext：检测中文字符时错误

riscv与x86均为相同错误

在测试中文字符时出错

```
+ python3 test.py
+ grep 你好
+ CHECK_RESULT 1 0 0 'test.py cannot be executed properly or Unable to filter necessary characters'
```

