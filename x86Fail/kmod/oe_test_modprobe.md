# oe_test_modprobe

x86 和 riscv 失败原因不同

在 riscv 上缺失 dm_cache 模块、 dm_mirror 模块和 dm_log 模块导致失败

在 x86 上，由于 dm-log 模块文件名为 dm-log.ko.xz ，故 ``find /usr/lib/modules/ -name dm-log.ko`` 无法找到模块导致失败。另外 dm_cache 模块无法载入 ``modprobe: ERROR: could not insert 'dm_cache': Key was rejected by service``

