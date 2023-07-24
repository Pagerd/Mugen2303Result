### oe_test _ima_v2_manual_gen_digest_01:无法初始化libselinux

riscv与x86均报相同错误

下为报错log

```
+ gen_digest_lists -t metadata -f compact -i l: -o add -p -1 -m immutable -i I:/tmp/test -d /tmp/ -i i: -i x:
Cannot initialize libselinux
Generator compact returned -1
```

