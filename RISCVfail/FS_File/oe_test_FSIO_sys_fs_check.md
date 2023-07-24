#### oe_test_FSIO_sys_fs_check

挂载硬盘时出错，显示硬盘不存在,下为log内对应报错部分

```
+ mount /dev/test_vggroup20230623013800/test_lv120230623022112 /tmp/ext420230623022112
mount: /tmp/ext420230623022112: special device /dev/test_vggroup20230623013800/test_lv120230623022112 does not exist.
+ CHECK_RESULT 32 0 0 'Mount failed.'
+ actual_result=32
+ expect_result=0
+ mode=0
+ error_log='Mount failed.'
```

### 