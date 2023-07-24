### oe_test_storage_lvm_merge_VG：未找到卷组“openeulerets”/没有预装对应软件

riscv上报错如下

```
vgextend openeulertest /dev/vdb -y
  Volume group "openeulertest" not found
  Cannot process volume group openeulertest
```

而x86则是没有安装vgextend所属软件

```
+ vgextend openeulertest /dev/sr0 -y
oe_test_storage_lvm_change_number.sh: line 30: vgextend: command not found
```

