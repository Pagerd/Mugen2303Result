### oe_test_ruby：测试套使用不支持的参数进行测试

riscv与x86报错相同

对应报错log如下

```
+ ruby -T1 ../common/hello.rb
+ grep 'Hello World!'
ruby: invalid option -T  (-h will show valid options) (RuntimeError)
```

ruby并无-T1参数