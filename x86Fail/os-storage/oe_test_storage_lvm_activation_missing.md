### oe_test_storage_lvm_activation_missing:未找到卷组“opentest”

riscv上为使用lvchange时报错

```
+ lvchange -ay opentest/test1 --activationmode degraded opentest
  Volume group "opentest" not found
  Cannot process volume group opentest
```

x86上则是未安装预装软件导致lvchange命令失效

```
+ lvchange -ay openeulertest/test --activationmode degraded openeulertest
oe_test_storage_lvm_activation_missing.sh: line 33: lvchange: command not found
```

