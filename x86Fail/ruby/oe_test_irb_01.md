### oe_test_irb_01：无法导入irbrc文件，数据输入中止

riscv与x86报错均相同

log内对应报错为

```
+ irb -d ../common/hello.rb
+ grep hello.rb
Exception `LoadError' at /usr/share/ruby/irb/init.rb:336 - cannot load such file -- /root/.irbrc
Exception `RubyLex::TerminateLineInput' at /usr/share/ruby/irb/ruby-lex.rb:270 - Terminate Line Input
+ CHECK_RESULT 1
+ actual_result=1
```

