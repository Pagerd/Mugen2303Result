### oe_test_grub2_mkconfig:测试环境log不同

riscv上报错内容为

```
 diff -Bw testlog1 testlog2
0a1
> /boot/extlinux/extlinux.conf:            kernel /vmlinuz-openEuler
+ CHECK_RESULT 1 0 0 'Files are different'
```

x86上报错内容为

```
+ diff -Bw testlog1 testlog2
1a2
> 	linux	/vmlinuz-6.1.19-7.0.0.17.oe2303.x86_64 root=UUID=5869c5b8-8da5-4fad-b809-b3e3b724020f ro console=tty1 console=ttyS0 rootfstype=ext4 quiet oops=panic softlockup_panic=1 nmi_watchdog=1 rd.shell=0 selinux=0 crashkernel=256M panic=3 
+ CHECK_RESULT 1 0 0 'Files are different'
```

同时riscv上未安装对应软件包

```
+ grub2-mkconfig -o tmp_grub_cfg
oe_test_grub2_mkconfig.sh: line 24: grub2-mkconfig: command not found
+ CHECK_RESULT 127 0 0 'Failed to execute grub2-mkconfig'
```

且riscv上没有测试所需文件tmp_grub_cfg

```
+ grep vmlinuz tmp_grub_cfg
grep: tmp_grub_cfg: No such file or directory
+ CHECK_RESULT 2 0 0 'Failed to find vmlinuz in tmp_grub_cfg'
```

