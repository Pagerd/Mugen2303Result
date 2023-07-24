### oe_test_fio_001:核心转储错误

riscv与x86报错均相同

下为报错log

```
+ fio-genzipf -i zipf theta -o 2 -c
oe_test_fio_001.sh: line 28:  2145 Segmentation fault      (core dumped) fio-genzipf -i zipf theta -o 2 -c
+ CHECK_RESULT 139 0 0 'fio-genzipf -i zipf theta -o 2 -c failed '
```

