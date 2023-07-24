# oe_test_osinfo-detect

测试套问题， x86 和 riscv 失败原因不同

测试套依赖 wget 命令，但是这个命令没有被显式安装，且在 x86 镜像没有被预装

在 riscv 上 ``osinfo-detect --format=env`` 参数有误

```
+ osinfo-detect --format=env openEuler-20.03-LTS-aarch64-dvd.iso
Error while parsing commandline options: Invalid value 'env'
Usage:
  osinfo-detect [OPTION…] - Detect if media is bootable and the relevant OS and distribution.

Help Options:
  -h, --help              Show help options

Application Options:
  -f, --format=FORMAT     Select the output format
  -t, --type=TYPE         Select the type of what is being detected
  -a, --all               Report all matches, not just the first

The only value available for FORMAT is 'plain', which means plain text.
TYPE can be either 'media' (the default) for CD/DVD ISOs,
or 'tree' for install trees.
```

