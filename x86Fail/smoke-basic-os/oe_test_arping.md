### oe_test_arping:无法更新临近主机arp缓存表

riscv与x86报错均相同

下为报错log

```
+ arping 127.0.0.1 -I -U -c 1
+ grep 'Sent 1 probes'
arping: Device -U not available.
.......
+ arping 127.0.0.1 -I -A -c 1
+ grep '1 broadcast'
arping: Device -A not available.
```

