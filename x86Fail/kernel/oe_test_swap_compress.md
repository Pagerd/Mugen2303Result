# oe_test_swap_compress

测试套问题， x86 和 riscv 失败原因一致

测试脚本如下

```
    default_swap=`free -lh |grep -i swap |awk '{print $2}' |awk -F"G" '{print $1}'`
    swapoff /dev/dm-1
    swap1=`free -lh |grep -i swap |awk '{print $2}' |awk -F"B" '{print $1}'`
    CHECK_RESULT $swap1 0 0 "Uninstall Failed"
    lvreduce -L -1G -f /dev/openeuler/swap
    mkswap /dev/openeuler/swap
    CHECK_RESULT $? 0 0 "Erase failed"
    swapon /dev/openeuler/swap
    swap2=`free -lh |grep -i swap |awk '{print $2}' |awk -F"G" '{print $1}'`
    [ `echo "${default_swap} > ${swap2}" |bc` -eq 1 ]
    CHECK_RESULT $? 0 0 "Compression failed"
```

其中 ``/dev/dm-1`` 没有提前建立直接使用，导致测试失败。

测试需要 lvreduce 命令，该命令依赖 lvm2 软件包，该软件包在 x86 和 riscv 的镜像均没有安装，且镜像不使用 lvm 。

