### oe_test_irb_03:跟踪器无法找到,debug出错

riscv与x86报错均相同

下为对应报错log

```
+ irb --tracer ../common/hello.rb
+ grep hello.rb:3
Tracer extension of IRB is enabled but tracer gem doesn't found.
```

在显示每次执行命令的跟踪时找不到跟踪器

```
+ irb --irb_debug 3 ../common/hello.rb
+ grep -E 'Tree|preproc|postproc'
/usr/share/ruby/irb/init.rb:318:in `parse_opts': Unrecognized switch: --irb_debug (IRB::UnrecognizedSwitch)
	from /usr/share/ruby/irb/init.rb:19:in `setup'
	from /usr/share/ruby/irb.rb:412:in `start'
	from /usr/share/gems/gems/irb-1.4.1/exe/irb:11:in `<top (required)>'
	from /usr/bin/irb:25:in `load'
	from /usr/bin/irb:25:in `<main>'
+ CHECK_RESULT 1
+ actual_result=1
```

在显示debug信息时出错s