### oe_test_ant_002

grep错误，grep加上选项`-P`之后参数以"\S"开头会造成grep错误：

```
[root@openeuler-riscv64 ant]# echo "1" | grep -P "\S"
grep: 程序错误
Aborted（核心已转储）
[root@openeuler-riscv64 ant]# echo "1" | grep -P "\Sasdf"
grep: 程序错误
Aborted（核心已转储）
```

