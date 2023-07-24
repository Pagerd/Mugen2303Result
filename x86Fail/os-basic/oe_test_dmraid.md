# oe_test_dmraid

## 共性的问题

测试套问题

``dmraid -s`` 输出为 ``no block devices found`` ，而测试脚本预期结果为 ``no raid disks`` ，导致没有判定出 raid 不存在。

## rv 独有的问题

在 riscv 上 ``dmraid -h`` 命令出现段错误 ``Segmentation fault (core dumped)`` 。

