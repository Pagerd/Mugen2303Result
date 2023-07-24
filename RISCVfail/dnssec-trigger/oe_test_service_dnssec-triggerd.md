##### oe_test_service_dnssec-triggerd:

内核模块缺失'gi',下为对应的log文件

```
May 30 19:07:18 openeuler-riscv64 dnssec-trigger-script[729]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:23 openeuler-riscv64 dnssec-trigger-script[735]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:24 openeuler-riscv64 dnssec-triggerd[736]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:35 openeuler-riscv64 dnssec-trigger-script[744]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:47 openeuler-riscv64 dnssec-trigger-script[752]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:51 openeuler-riscv64 dnssec-trigger-script[755]: ModuleNotFoundError: No module named 'gi'
May 30 19:07:52 openeuler-riscv64 dnssec-triggerd[756]: ModuleNotFoundError: No module named 'gi'
```

手动执行指令时出现如下错误

```
‘/etc/systemd/system/multi-user.target.wants/dnssec-triggerd.service’: No such file or directory
```

### 