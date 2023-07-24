# oe_test_io_sched

测试套问题，x86 和 riscv 失败原因一致，没有考虑 qemu 环境

测试脚本如下

```
    grep CONFIG_DEFAULT_IOSCHED /boot/config-`uname -r`
    CHECK_RESULT $? 0 0 "Query failed"
    test_name=(none mq-deadline bfq kyber)
    for i in ${test_name[*]}
    do
      echo $i > /sys/block/sda/queue/scheduler
      model=`grep $i /sys/block/sda/queue/scheduler |awk -F "[" '{print $2}' |awk -F "]" '{print $1}'`
      CHECK_RESULT $model $i 0 "Switching failed"
    done
```

其中 ``sda``` 为实体机中的磁盘名称，而在 qemu 中为 ``vda`` ，故在 qemu 中无法用这个测试脚本进行测试

