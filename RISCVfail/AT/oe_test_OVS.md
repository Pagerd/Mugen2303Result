### oe_test_OVS

pre_test阶段执行`systemctl start openvswitch`失败，原因为找不到内核模块：

```
6月 08 16:35:37 openeuler-riscv64 ovs-ctl[2343]: Inserting openvswitch module
6月 08 16:35:37 openeuler-riscv64 ovs-ctl[2350]: modprobe: FATAL: Module openvswitch not found in directory /lib/modules/6.1.8-3.oe2303.riscv64
6月 08 16:35:37 openeuler-riscv64 ovs-ctl[2343]: [FAILED]
6月 08 16:35:37 openeuler-riscv64 systemd[1]: ovs-vswitchd.service: Control process exited, code=exited, status=1/FAILURE
```

之后在测试阶段执行命令`ovs-vsctl add-br br0`时会直接卡住直到超时。