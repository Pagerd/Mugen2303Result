### oe_test_ndisc_rdisc6:测试超时

riscv与x86相同错误

下为对应报错log

```
+ /usr/bin/time -o runtime rdisc6 -r 1 -w 2000 fe80::3afe:c976:9125:1e46 ens4
Soliciting fe80::3afe:c976:9125:1e46 (fe80::3afe:c976:9125:1e46) on ens4...
Timed out.
No response.
```

