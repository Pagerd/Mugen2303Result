# oe_test_service_lm_sensors

qemu 环境不适合测试

日志如下

```
+ grep 'no sensors were detected' /tmp/sensors_log
Sorry, no sensors were detected.
Sorry, no sensors were detected.
+ LOG_ERROR 'The environment does not support testing'
+ message='The environment does not support testing'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'The environment does not support testing'
Wed Jun  7 10:59:24 2023 - ERROR - The environment does not support testing
```

## riscv 独有的问题

缺失 i2c-dev 和 cpuid 内核模块

```
modprobe: FATAL: Module cpuid not found in directory /lib/modules/6.1.19-2.oe2303.riscv64
modprobe: FATAL: Module i2c-dev not found in directory /lib/modules/6.1.19-2.oe2303.riscv64
```

