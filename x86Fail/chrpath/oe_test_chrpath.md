### oe_test_chrpath:路径下没有对应文件

riscv与x86报错相同

对应报错log如下

```
+ chrpath -r /usr/lib64/ man
man: no rpath or runpath tag found.
+ grep PATH=/usr/lib64/
+ chrpath -l man
+ CHECK_RESULT 1 0 0 'Failed to change search path'
```

