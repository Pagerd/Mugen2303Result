# oe_test_nmcli_macsec

x86 和 riscv 在同一条命令出错，报错信息略有不同。

riscv:

```
+ nmcli connection up test-macsec+
Error: Connection activation failed: macsec0 failed to create resources: Failed to create macsec interface 'macsec0' for 'test-macsec+': Operation not supported
```

x86:

```
+ nmcli connection up test-macsec+
Error: Connection activation failed: 802.1X supplicant failed
Hint: use 'journalctl -xe NM_CONNECTION=868b5976-c164-4ef5-99a7-73391b9130ff + NM_DEVICE=macsec0' to get more details.
```
测试脚本没有给出 journalctl 日志

