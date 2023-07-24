### oe_test_pesign_efikeygen：CA证书错误/没有安装对应软件

riscv在使用efikeygen时出现错误

```
+ efikeygen -d ./demo -C -S -n 'ALT Linux UEFI SB CA' -c 'CN=ALT UEFI SB CA 2013,OU=ALT Certification Authority,O=ALT Linux Team,C=RU' -u http://www.baidu.com -k -s 00
+ grep 'tag: 369'
efikeygen: CA certificates cannot have kernel or module signing credentials.
```

而x86没有预装unzip，因此无法解压测试文件进行测试

```
+ unzip baidu.zip
oe_test_pesign_base_02.sh: line 29: unzip: command not found
```

