# oe_test_mtx_loaderinfo
# oe_test_mtx_tapeinfo
# oe_test_mtx_mtx
# oe_test_mtx_scsieject
# oe_test_mtx_scsitape

测试套问题，x86 和 riscv 失败原因基本一致，测试在初始化部分就失败了

测试在初始化阶段编译 mhvtl-utils 软件包，但是这个软件包依赖 kernel-devel ，这个软件包在 riscv 和 x86 镜像都没有预装；这个软件包同时依赖 gcc ，但是这个软件包在 x86 镜像没有预装

riscv 失败日志

```
+ rpmbuild -bb ./tmp/mhvtl/mhvtl-utils.spec
warning: bogus date in %changelog: Wed Dec 22 2022 lutkunpeng <lutkunpeng@163.com> - 1.7-3
error: Failed build dependencies:
	kernel-devel is needed by mhvtl-utils-1.7-3.riscv64
```

x86 失败日志

```
+ rpmbuild -bb ./tmp/mhvtl/mhvtl-utils.spec
warning: bogus date in %changelog: Wed Dec 22 2022 lutkunpeng <lutkunpeng@163.com> - 1.7-3
error: Failed build dependencies:
	gcc is needed by mhvtl-utils-1.7-3.x86_64
	kernel-devel is needed by mhvtl-utils-1.7-3.x86_64
```

