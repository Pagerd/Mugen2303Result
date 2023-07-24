### oe_test_pesign_base_02:找不到证书/没有安装对应软件

riscv在调用命令时出现以下错误

```
+ pesign -i grubx64.efi.signed -n ./baidu -C out4 -c 'ALT Linux UEFI SB CA'
cms_common.c:find_certificate:718: could not find certificate:SEC_ERROR_INVALID_ARGS:security library: invalid arguments.
```

而x86没有预装unzip，因此无法解压测试文件进行测试

```
+ unzip baidu.zip
oe_test_pesign_base_02.sh: line 29: unzip: command not found
```

