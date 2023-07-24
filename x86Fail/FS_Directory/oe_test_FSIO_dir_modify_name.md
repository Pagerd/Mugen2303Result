### oe_test_FSIO_dir_modify_name:测试文件失败

riscv与x86报错相同

下为对应报错log

```
+ mv /tmp/point120230428215644/test2 /tmp/point120230428215644/test2_mod
+ test -f /tmp/point120230428215644/test2_mod
+ CHECK_RESULT 1 0 0 'Check file in ext3 failed.'
```

同时riscv有额外的device报错

```
++ msg='test_vggroup20230428215305 /tmp/point120230428215644 /tmp/point220230428215644 '
++ count=3
++ for fs in ${fs_type[@]}
++ lvname=test_lv320230428215644
++ point=/tmp/point320230428215644
++ lvcreate -n test_lv320230428215644 -L 512M test_vggroup20230428215305 -y
  Volume group "test_vggroup20230428215305" has insufficient free space (124 extents): 128 required.
++ mkfs -t xfs /dev/test_vggroup20230428215305/test_lv320230428215644
Error accessing specified device /dev/test_vggroup20230428215305/test_lv320230428215644: No such file or directory
Usage: mkfs.xfs
```

