### oe_test_hwloc_1.11.9_hwloc-assembler:不支持hwloc-assembler命令

riscv与x86报错相同，对应log如下

```
+ hwloc-assembler ./tmp/output.xml --name host1 ./common/host1.xml --name host2 ./common/host2.xml
oe_test_hwloc_1.11.9_hwloc-assembler.sh: line 31: hwloc-assembler: command not found
+ CHECK_RESULT 127 0 0 'hwloc-assembler --name  failed'
+ actual_result=127
```

推测为当前版本不支持hwloc-assembler命令
