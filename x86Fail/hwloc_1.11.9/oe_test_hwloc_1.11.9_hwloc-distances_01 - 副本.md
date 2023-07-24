### oe_test_hwloc_1.11.9_hwloc-distances_01:不支持hwloc-distances命令

riscv与x86报错相同，log如下

```
+ hwloc-distances -l -i ./common/distances_test.xml
oe_test_hwloc_1.11.9_hwloc-distances_01.sh: line 30: hwloc-distances: command not found
+ grep 'below Machine L#0'
+ CHECK_RESULT 1 0 0 'hwloc-distances -l  failed'
```

推测为当前版本不支持hwloc-assembler命令
