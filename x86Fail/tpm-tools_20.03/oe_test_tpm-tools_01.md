### oe_test_tpm-tools_01:未开启tpmd和tcsd

riscv与x86均报相同错误：

```
spawn tpm_getpubek
Tspi_Context_Connect failed: 0x00003011 - layer=tsp, code=0011 (17), Communication failure
expect: spawn id exp4 not open
    while executing
"expect eof"
+ grep -i '[0-9a-z]' log_getpubek1
```

推测原因为未开启tpmd和tcsd