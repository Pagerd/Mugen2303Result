# oe_test_catman

riscv 和 x86 上错误测试基本一样

``catman 1|grep "ab"`` 命令均没有 ``grep`` 到 ``ab`` 字串， ``catman -C 1|grep -E "ab.*aio"`` 同样没有匹配。

riscv 上 ``catman -d|grep man`` 命令偶现失败，可以参考 [2023-04-28-03:30:09.log](https://github.com/KotorinMinami/res_list/tree/master/mugen-riscv/logs/os-basic/oe_test_catman/2023-04-28-03:30:09.log) 和 [2023-07-19-11_08_39.log](https://github.com/KotorinMinami/res_list/tree/master/mugen-riscv/logs/os-basic/oe_test_catman/2023-07-19-11_08_39.log) 两份测试日志。

