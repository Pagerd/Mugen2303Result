# oe_test_count_gperftools_function

测试套问题，测试套只显式安装了 gperftools 软件包，实际上还依赖 gperftools-devel 和 gcc-g++ 软件包

其中 gperftools-devel 软件包在 x86 和 riscv 上均没有预装； gcc-g++ 软件包在 x86 镜像上没有预装。

