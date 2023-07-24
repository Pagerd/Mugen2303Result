# oe_test_dmidecode

测试 dmidecode 命令，依赖 dmidecode 软件包，测试套没有显示安装 dmidecode 软件包，而该软件包在 x86 和 riscv 镜像都没有预装

```
+ dmidecode -h
+ grep -i 'Usage: dmidecode'
oe_test_dmidecode.sh: line 25: dmidecode: command not found
```

