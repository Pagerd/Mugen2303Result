### oe_test_ethtool_01：测试命令集不支持

riscv与x86报错log并不相同

riscv为测试环境未安装ethtool

```
++ grep generic-segmentation-offload:
oe_test_ethtool_01.sh: line 24: ethtool: command not found
++ awk '{print $NF}'
```

x86为使用了不支持或现版本不存在的测试命令

```
++ ethtool -k
++ grep generic-segmentation-offload:
++ awk '{print $NF}'
ethtool: bad command line argument(s)
For more information run ethtool -h
..............
+ ethtool -K sg on
ethtool (-K): flag '(null)' for parameter '(null)' is not followed by 'on' or 'off'
+ ethtool -K gso on
ethtool (-K): flag '(null)' for parameter '(null)' is not followed by 'on' or 'off'
```

