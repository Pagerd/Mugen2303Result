### oe_test_aspell_01

1. x86的openeuler上没有预装unzip，所以pre_test()中的`unzip common/aspell6-en-2020.12.07-0.zip`指令执行失败。
2. 现在执行命令`echo aaa | aspell -a`之后输出的词汇有31个，所以开头变成了`& aaa 31 0:`，而不是`& aaa 15 0:`，所以命令`echo aaa | aspell -a | grep "& aaa 15 0:"`执行失败