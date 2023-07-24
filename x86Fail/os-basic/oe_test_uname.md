# oe_test_uname

测试套问题，测试套完全没有考虑 riscv 架构导致在 riscv 测试失败

```
uname -m | grep -E "aarch64|x86_64"
```

测试套问题，测试套依赖 ``hostname`` 命令，而这个命令所在 hostname 软件包在 riscv 镜像预装了，在 x86 镜像上没有预装，导致在 x86 上测试失败

```
uname -n | grep $(hostname)

+ uname -n
++ hostname
oe_test_uname.sh: line 27: hostname: command not found
+ grep
Usage: grep [OPTION]... PATTERNS [FILE]...
Try 'grep --help' for more information.
```

