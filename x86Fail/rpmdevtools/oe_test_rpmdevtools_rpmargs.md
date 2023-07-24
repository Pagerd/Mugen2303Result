### oe_test_rpmdevtools_rpmargs:部分参数测试错误



riscv对应log如下



```
+ rpmdev-checksig ModemManager-glib-1.18.12-1.oe2303.riscv64.rpm
+ CHECK_RESULT 1 0 0 'Failed command:rpmdev-checksig'
```



x86对应log如下

```
+ test -d ./tmp_dir/NetworkManager-1.32.12-16.oe2303.x86_64 ./tmp_dir/NetworkManager-libnm-1.32.12-16.oe2303.x86_64
oe_test_rpmdevtools_rpmargs.sh: line 78: test: ./tmp_dir/NetworkManager-1.32.12-16.oe2303.x86_64: binary operator expected
+ CHECK_RESULT 2 0 0 'Failed option: -C'
+ actual_result=2
+ expect_result=0
+ mode=0
+ error_log='Failed option: -C'
+ exit_mode=0
+ '[' -z 2 ']'
+ '[' 0 -eq 0 ']'
+ test 2x '!=' 0x
+ test -n 'Failed option: -C'
+ LOG_ERROR 'Failed option: -C'
+ message='Failed option: -C'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'Failed option: -C'
Fri May  5 00:37:51 2023 - ERROR - Failed option: -C
```

