### oe_test_service_strongswan_01:riscv堆栈错误，x86 openssl加载失败

riscv中在使用stop命令时出现错误

```
+ podman stop -all
runtime: lfstack.push invalid packing: node=0xffffff92bc1520 cnt=0x1 packed=0xffff92bc15200001 -> node=0xffff92bc1520
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaad9223310?, 0xaaaaaad8321f40?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffcdb54808 sp=0xffffffcdb547e0 pc=0xaaaaaad831d1ec
runtime.(*lfstack).push(0xc000052f00?, 0xffffff92bc1520)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffcdb54838 sp=0xffffffcdb54808 pc=0xaaaaaad82f0d98
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaada5d0ff8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffcdb54868 sp=0xffffffcdb54838 pc=0xaaaaaad8317010
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffcdb548a0 sp=0xffffffcdb54868 pc=0xaaaaaad830aa58
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffcdb548a8 sp=0xffffffcdb548a0 pc=0xaaaaaad82ff908
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffcdb548b0 sp=0xffffffcdb548a8 pc=0xaaaaaad834b484

goroutine 1 [running, locked to thread]:
runtime.systemstack_switch()
	/usr/lib/golang/src/runtime/asm_riscv64.s:96 +0x8 fp=0xc00059f8f0 sp=0xc00059f8e8 pc=0xaaaaaad834b418
runtime.gcStart({0xffffff92bb25b8?, 0x59?, 0xd82f27e0?})
	/usr/lib/golang/src/runtime/mgc.go:667 +0x358 fp=0xc00059f980 sp=0xc00059f8f0 pc=0xaaaaaad82ffc80
runtime.mallocgc(0x1000, 0xaaaaaad95fe240, 0x1)
	/usr/lib/golang/src/runtime/malloc.go:1148 +0x6a8 fp=0xc00059f9f8 sp=0xc00059f980 pc=0xaaaaaad82f29b0
runtime.makeslice(0x3000?, 0x3000?, 0xc00035befb?)
	/usr/lib/golang/src/runtime/slice.go:103 +0x70 fp=0xc00059fa18 sp=0xc00059f9f8 pc=0xaaaaaad83354c0
bufio.NewWriterSize(...)
	/usr/lib/golang/src/bufio/bufio.go:593
bufio.NewWriter(...)
	/usr/lib/golang/src/bufio/bufio.go:602
encoding/csv.NewWriter(...)
	/usr/lib/golang/src/encoding/csv/writer.go:40
github.com/containers/podman/vendor/github.com/spf13/pflag.writeAsCSV({0xaaaaaada5d7d20, 0x0, 0x0})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:33 +0x70 fp=0xc00059faa8 sp=0xc00059fa18 pc=0xaaaaaad881b898
github.com/containers/podman/vendor/github.com/spf13/pflag.(*stringArrayValue).String(0xaaaaaada5a7140?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_array.go:57 +0x3c fp=0xc00059fae8 sp=0xc00059faa8 pc=0xaaaaaad881b094
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarPF(0xaaaaaad9143c94?, {0xaaaaaad9886cb8, 0xc000314180}, {0xaaaaaad9216eca, 0x5}, {0x0, 0x0}, {0xaaaaaad9292f7d, 0x37})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:829 +0x94 fp=0xc00059fb28 sp=0xc00059fae8 pc=0xaaaaaad880f6e4
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarP(...)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:837
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).StringArrayVar(0x0?, 0xaaaaaada5a7f50, {0xaaaaaad9216eca, 0x5}, {0xaaaaaada5d7d20, 0x0, 0x0}, {0xaaaaaad9292f7d, 0x37})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_array.go:83 +0x120 fp=0xc00059fb80 sp=0xc00059fb28 pc=0xaaaaaad881b388
github.com/containers/podman/cmd/podman/common.DefineCreateFlags(0xaaaaaada50b1e0?, 0xaaaaaada5a79c0, 0x0)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/common/create.go:617 +0x19b4 fp=0xc00059fc68 sp=0xc00059fb80 pc=0xaaaaaad9143ccc
github.com/containers/podman/cmd/podman/containers.createFlags(0xaaaaaad96ee100?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:71 +0x7c fp=0xc00059fcc0 sp=0xc00059fc68 pc=0xaaaaaad9152fac
github.com/containers/podman/cmd/podman/containers.init.6()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:93 +0xd8 fp=0xc00059fd20 sp=0xc00059fcc0 pc=0xaaaaaad9153130
runtime.doInit(0xaaaaaada54e840)
	/usr/lib/golang/src/runtime/proc.go:6329 +0x134 fp=0xc00059fe50 sp=0xc00059fd20 pc=0xaaaaaad832d08c
runtime.doInit(0xaaaaaada549c40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc00059ff80 sp=0xc00059fe50 pc=0xaaaaaad832cfcc
runtime.main()
	/usr/lib/golang/src/runtime/proc.go:233 +0x1d0 fp=0xc00059ffd8 sp=0xc00059ff80 pc=0xaaaaaad831f7d0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00059ffd8 sp=0xc00059ffd8 pc=0xaaaaaad834d694

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005efb0 sp=0xc00005ef98 pc=0xaaaaaad831fc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.forcegchelper()
	/usr/lib/golang/src/runtime/proc.go:302 +0xb0 fp=0xc00005efd8 sp=0xc00005efb0 pc=0xaaaaaad831fa90
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005efd8 sp=0xc00005efd8 pc=0xaaaaaad834d694
created by runtime.init.5
	/usr/lib/golang/src/runtime/proc.go:290 +0x28

goroutine 18 [GC sweep wait]:
runtime.gopark(0x1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005a798 sp=0xc00005a780 pc=0xaaaaaad831fc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.bgsweep(0x0?)
	/usr/lib/golang/src/runtime/mgcsweep.go:297 +0x114 fp=0xc00005a7c8 sp=0xc00005a798 pc=0xaaaaaad830ac04
runtime.gcenable.func1()
	/usr/lib/golang/src/runtime/mgc.go:178 +0x2c fp=0xc00005a7d8 sp=0xc00005a7c8 pc=0xaaaaaad82ff3d4
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005a7d8 sp=0xc00005a7d8 pc=0xaaaaaad834d694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:178 +0x70

goroutine 19 [GC scavenge wait]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x412e848000000000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005af80 sp=0xc00005af68 pc=0xaaaaaad831fc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.(*scavengerState).park(0xaaaaaada5a56a0)
	/usr/lib/golang/src/runtime/mgcscavenge.go:389 +0x68 fp=0xc00005afa8 sp=0xc00005af80 pc=0xaaaaaad8308b30
runtime.bgscavenge(0x0?)
	/usr/lib/golang/src/runtime/mgcscavenge.go:622 +0x6c fp=0xc00005afc8 sp=0xc00005afa8 pc=0xaaaaaad830909c
runtime.gcenable.func2()
	/usr/lib/golang/src/runtime/mgc.go:179 +0x2c fp=0xc00005afd8 sp=0xc00005afc8 pc=0xaaaaaad82ff374
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005afd8 sp=0xc00005afd8 pc=0xaaaaaad834d694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:179 +0xb0

goroutine 34 [finalizer wait]:
runtime.gopark(0x3000?, 0x18000?, 0x0?, 0x30?, 0x3000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005e5a8 sp=0xc00005e590 pc=0xaaaaaad831fc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.runfinq()
	/usr/lib/golang/src/runtime/mfinal.go:180 +0x110 fp=0xc00005e7d8 sp=0xc00005e5a8 pc=0xaaaaaad82fe5c8
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005e7d8 sp=0xc00005e7d8 pc=0xaaaaaad834d694
created by runtime.createfing
	/usr/lib/golang/src/runtime/mfinal.go:157 +0x64

goroutine 35 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc0004c8748 sp=0xc0004c8730 pc=0xaaaaaad831fc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0004c87d8 sp=0xc0004c8748 pc=0xaaaaaad83015c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0004c87d8 sp=0xc0004c87d8 pc=0xaaaaaad834d694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 3 [GC worker (idle)]:
runtime.gopark(0x9064169532?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005f748 sp=0xc00005f730 pc=0xaaaaaad831fc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005f7d8 sp=0xc00005f748 pc=0xaaaaaad83015c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005f7d8 sp=0xc00005f7d8 pc=0xaaaaaad834d694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 4 [GC worker (idle)]:
runtime.gopark(0xaaaaaada5d94c0?, 0x3?, 0xd3?, 0xde?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005ff48 sp=0xc00005ff30 pc=0xaaaaaad831fc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005ffd8 sp=0xc00005ff48 pc=0xaaaaaad83015c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005ffd8 sp=0xc00005ffd8 pc=0xaaaaaad834d694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 5 [GC worker (idle)]:
runtime.gopark(0x9063fe1794?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000060748 sp=0xc000060730 pc=0xaaaaaad831fc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0000607d8 sp=0xc000060748 pc=0xaaaaaad83015c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000607d8 sp=0xc0000607d8 pc=0xaaaaaad834d694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 22 [chan receive]:
runtime.gopark(0xc000062c00?, 0xaaaaaad8325f0c?, 0x0?, 0x0?, 0xc000105501?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc0000616d8 sp=0xc0000616c0 pc=0xaaaaaad831fc08
runtime.chanrecv(0xc0005220c0, 0xc0000617b0, 0xc0?)
	/usr/lib/golang/src/runtime/chan.go:583 +0x498 fp=0xc000061768 sp=0xc0000616d8 pc=0xaaaaaad82ecaf0
runtime.chanrecv2(0x12a05f200?, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:447 +0x14 fp=0xc000061788 sp=0xc000061768 pc=0xaaaaaad82ec644
github.com/containers/podman/vendor/k8s.io/klog/v2.(*loggingT).flushDaemon(0xc000124420?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:1169 +0x6c fp=0xc0000617c8 sp=0xc000061788 pc=0xaaaaaad8d3c8b4
github.com/containers/podman/vendor/k8s.io/klog/v2.init.0.func1()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x2c fp=0xc0000617d8 sp=0xc0000617c8 pc=0xaaaaaad8d3a6bc
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000617d8 sp=0xc0000617d8 pc=0xaaaaaad834d694
created by github.com/containers/podman/vendor/k8s.io/klog/v2.init.0
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x124
++ podman ps -qa
runtime: lfstack.push invalid packing: node=0xffffffa91ef520 cnt=0x1 packed=0xffffa91ef5200001 -> node=0xffffa91ef520
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaae9ff9310?, 0xaaaaaae90f7f40?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffc5e7a808 sp=0xffffffc5e7a7e0 pc=0xaaaaaae90f31ec
runtime.(*lfstack).push(0xc000050a00?, 0xffffffa91ef520)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffc5e7a838 sp=0xffffffc5e7a808 pc=0xaaaaaae90c6d98
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaaeb3a6ff8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffc5e7a868 sp=0xffffffc5e7a838 pc=0xaaaaaae90ed010
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffc5e7a8a0 sp=0xffffffc5e7a868 pc=0xaaaaaae90e0a58
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffc5e7a8a8 sp=0xffffffc5e7a8a0 pc=0xaaaaaae90d5908
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffc5e7a8b0 sp=0xffffffc5e7a8a8 pc=0xaaaaaae9121484

goroutine 1 [running, locked to thread]:
runtime.systemstack_switch()
	/usr/lib/golang/src/runtime/asm_riscv64.s:96 +0x8 fp=0xc00059f8f0 sp=0xc00059f8e8 pc=0xaaaaaae9121418
runtime.gcStart({0xffffffa91e0f18?, 0x59?, 0xe90c87e0?})
	/usr/lib/golang/src/runtime/mgc.go:667 +0x358 fp=0xc00059f980 sp=0xc00059f8f0 pc=0xaaaaaae90d5c80
runtime.mallocgc(0x1000, 0xaaaaaaea3d4240, 0x1)
	/usr/lib/golang/src/runtime/malloc.go:1148 +0x6a8 fp=0xc00059f9f8 sp=0xc00059f980 pc=0xaaaaaae90c89b0
runtime.makeslice(0x3000?, 0xc0004277b6?, 0xc0004277b7?)
	/usr/lib/golang/src/runtime/slice.go:103 +0x70 fp=0xc00059fa18 sp=0xc00059f9f8 pc=0xaaaaaae910b4c0
bufio.NewWriterSize(...)
	/usr/lib/golang/src/bufio/bufio.go:593
bufio.NewWriter(...)
	/usr/lib/golang/src/bufio/bufio.go:602
encoding/csv.NewWriter(...)
	/usr/lib/golang/src/encoding/csv/writer.go:40
github.com/containers/podman/vendor/github.com/spf13/pflag.writeAsCSV({0xaaaaaaeb3add20, 0x0, 0x0})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:33 +0x70 fp=0xc00059faa8 sp=0xc00059fa18 pc=0xaaaaaae95f1898
github.com/containers/podman/vendor/github.com/spf13/pflag.(*stringSliceValue).String(0xaaaaaaeb37d140?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:61 +0x3c fp=0xc00059fae8 sp=0xc00059faa8 pc=0xaaaaaae95f1bfc
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarPF(0xaaaaaae9f184a8?, {0xaaaaaaea65cce8, 0xc0004d00a0}, {0xaaaaaae9ff1bba, 0x8}, {0x0, 0x0}, {0xaaaaaaea031615, 0x24})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:829 +0x94 fp=0xc00059fb28 sp=0xc00059fae8 pc=0xaaaaaae95e56e4
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarP(...)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:837
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).StringSliceVar(0x0?, 0xaaaaaaeb37da40, {0xaaaaaae9ff1bba, 0x8}, {0xaaaaaaeb3add20, 0x0, 0x0}, {0xaaaaaaea031615, 0x24})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:105 +0x120 fp=0xc00059fb80 sp=0xc00059fb28 pc=0xaaaaaae95f2078
github.com/containers/podman/cmd/podman/common.DefineCreateFlags(0xaaaaaaeb2e11e0?, 0xaaaaaaeb37d9c0, 0x0)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/common/create.go:72 +0x28c fp=0xc00059fc68 sp=0xc00059fb80 pc=0xaaaaaae9f185a4
github.com/containers/podman/cmd/podman/containers.createFlags(0xaaaaaaea4c4100?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:71 +0x7c fp=0xc00059fcc0 sp=0xc00059fc68 pc=0xaaaaaae9f28fac
github.com/containers/podman/cmd/podman/containers.init.6()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:93 +0xd8 fp=0xc00059fd20 sp=0xc00059fcc0 pc=0xaaaaaae9f29130
runtime.doInit(0xaaaaaaeb324840)
	/usr/lib/golang/src/runtime/proc.go:6329 +0x134 fp=0xc00059fe50 sp=0xc00059fd20 pc=0xaaaaaae910308c
runtime.doInit(0xaaaaaaeb31fc40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc00059ff80 sp=0xc00059fe50 pc=0xaaaaaae9102fcc
runtime.main()
	/usr/lib/golang/src/runtime/proc.go:233 +0x1d0 fp=0xc00059ffd8 sp=0xc00059ff80 pc=0xaaaaaae90f57d0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00059ffd8 sp=0xc00059ffd8 pc=0xaaaaaae9123694

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005efb0 sp=0xc00005ef98 pc=0xaaaaaae90f5c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.forcegchelper()
	/usr/lib/golang/src/runtime/proc.go:302 +0xb0 fp=0xc00005efd8 sp=0xc00005efb0 pc=0xaaaaaae90f5a90
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005efd8 sp=0xc00005efd8 pc=0xaaaaaae9123694
created by runtime.init.5
	/usr/lib/golang/src/runtime/proc.go:290 +0x28

goroutine 3 [GC sweep wait]:
runtime.gopark(0x1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005f798 sp=0xc00005f780 pc=0xaaaaaae90f5c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.bgsweep(0x0?)
	/usr/lib/golang/src/runtime/mgcsweep.go:297 +0x114 fp=0xc00005f7c8 sp=0xc00005f798 pc=0xaaaaaae90e0c04
runtime.gcenable.func1()
	/usr/lib/golang/src/runtime/mgc.go:178 +0x2c fp=0xc00005f7d8 sp=0xc00005f7c8 pc=0xaaaaaae90d53d4
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005f7d8 sp=0xc00005f7d8 pc=0xaaaaaae9123694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:178 +0x70

goroutine 4 [GC scavenge wait]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x412e848000000000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005ff80 sp=0xc00005ff68 pc=0xaaaaaae90f5c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.(*scavengerState).park(0xaaaaaaeb37b6a0)
	/usr/lib/golang/src/runtime/mgcscavenge.go:389 +0x68 fp=0xc00005ffa8 sp=0xc00005ff80 pc=0xaaaaaae90deb30
runtime.bgscavenge(0x0?)
	/usr/lib/golang/src/runtime/mgcscavenge.go:622 +0x6c fp=0xc00005ffc8 sp=0xc00005ffa8 pc=0xaaaaaae90df09c
runtime.gcenable.func2()
	/usr/lib/golang/src/runtime/mgc.go:179 +0x2c fp=0xc00005ffd8 sp=0xc00005ffc8 pc=0xaaaaaae90d5374
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005ffd8 sp=0xc00005ffd8 pc=0xaaaaaae9123694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:179 +0xb0

goroutine 18 [finalizer wait]:
runtime.gopark(0x3000?, 0x18000?, 0x0?, 0x30?, 0x3000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005e5a8 sp=0xc00005e590 pc=0xaaaaaae90f5c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.runfinq()
	/usr/lib/golang/src/runtime/mfinal.go:180 +0x110 fp=0xc00005e7d8 sp=0xc00005e5a8 pc=0xaaaaaae90d45c8
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005e7d8 sp=0xc00005e7d8 pc=0xaaaaaae9123694
created by runtime.createfing
	/usr/lib/golang/src/runtime/mfinal.go:157 +0x64

goroutine 19 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005a748 sp=0xc00005a730 pc=0xaaaaaae90f5c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005a7d8 sp=0xc00005a748 pc=0xaaaaaae90d75c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005a7d8 sp=0xc00005a7d8 pc=0xaaaaaae9123694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 5 [GC worker (idle)]:
runtime.gopark(0x90b4d39142?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000060748 sp=0xc000060730 pc=0xaaaaaae90f5c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0000607d8 sp=0xc000060748 pc=0xaaaaaae90d75c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000607d8 sp=0xc0000607d8 pc=0xaaaaaae9123694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 6 [GC worker (idle)]:
runtime.gopark(0xaaaaaaea64d830?, 0xc000040040?, 0x18?, 0x14?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000060f48 sp=0xc000060f30 pc=0xaaaaaae90f5c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc000060fd8 sp=0xc000060f48 pc=0xaaaaaae90d75c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000060fd8 sp=0xc000060fd8 pc=0xaaaaaae9123694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 7 [GC worker (idle)]:
runtime.gopark(0x90b4d8290e?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000061748 sp=0xc000061730 pc=0xaaaaaae90f5c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0000617d8 sp=0xc000061748 pc=0xaaaaaae90d75c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000617d8 sp=0xc0000617d8 pc=0xaaaaaae9123694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 35 [chan receive]:
runtime.gopark(0xc000062800?, 0xaaaaaae90fbf0c?, 0x0?, 0x0?, 0xc000102b01?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000061ed8 sp=0xc000061ec0 pc=0xaaaaaae90f5c08
runtime.chanrecv(0xc000118000, 0xc000061fb0, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:583 +0x498 fp=0xc000061f68 sp=0xc000061ed8 pc=0xaaaaaae90c2af0
runtime.chanrecv2(0x12a05f200?, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:447 +0x14 fp=0xc000061f88 sp=0xc000061f68 pc=0xaaaaaae90c2644
github.com/containers/podman/vendor/k8s.io/klog/v2.(*loggingT).flushDaemon(0xc0001a6120?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:1169 +0x6c fp=0xc000061fc8 sp=0xc000061f88 pc=0xaaaaaae9b128b4
github.com/containers/podman/vendor/k8s.io/klog/v2.init.0.func1()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x2c fp=0xc000061fd8 sp=0xc000061fc8 pc=0xaaaaaae9b106bc
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000061fd8 sp=0xc000061fd8 pc=0xaaaaaae9123694
created by github.com/containers/podman/vendor/k8s.io/klog/v2.init.0
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x124
+ podman rm -f
runtime: lfstack.push invalid packing: node=0xffffff833f3520 cnt=0x1 packed=0xffff833f35200001 -> node=0xffff833f3520
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaae8b2c310?, 0xaaaaaae7c2af40?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffdd5c1808 sp=0xffffffdd5c17e0 pc=0xaaaaaae7c261ec
runtime.(*lfstack).push(0xc00004e500?, 0xffffff833f3520)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffdd5c1838 sp=0xffffffdd5c1808 pc=0xaaaaaae7bf9d98
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaae9ed9ff8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffdd5c1868 sp=0xffffffdd5c1838 pc=0xaaaaaae7c20010
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffdd5c18a0 sp=0xffffffdd5c1868 pc=0xaaaaaae7c13a58
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffdd5c18a8 sp=0xffffffdd5c18a0 pc=0xaaaaaae7c08908
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffdd5c18b0 sp=0xffffffdd5c18a8 pc=0xaaaaaae7c54484

goroutine 1 [running, locked to thread]:
runtime.systemstack_switch()
	/usr/lib/golang/src/runtime/asm_riscv64.s:96 +0x8 fp=0xc00059f858 sp=0xc00059f850 pc=0xaaaaaae7c54418
runtime.gcStart({0xffffff833e4108?, 0xffffff5a5dd30d?, 0xe9ede1a8?})
	/usr/lib/golang/src/runtime/mgc.go:667 +0x358 fp=0xc00059f8e8 sp=0xc00059f858 pc=0xaaaaaae7c08c80
runtime.mallocgc(0x40, 0xaaaaaae8f07240, 0x1)
	/usr/lib/golang/src/runtime/malloc.go:1148 +0x6a8 fp=0xc00059f960 sp=0xc00059f8e8 pc=0xaaaaaae7bfb9b0
runtime.makeslice(0xffffff833e4108?, 0x59?, 0xaaaaaae8f5b9a0?)
	/usr/lib/golang/src/runtime/slice.go:103 +0x70 fp=0xc00059f980 sp=0xc00059f960 pc=0xaaaaaae7c3e4c0
bytes.(*Buffer).grow(0xc0003fe0f0, 0x1)
	/usr/lib/golang/src/bytes/buffer.go:128 +0x1a8 fp=0xc00059f9b0 sp=0xc00059f980 pc=0xaaaaaae7cea6c0
bytes.(*Buffer).Write(0xc0003fe0f0, {0xc000402000, 0x1, 0xaaaaaae8124898?})
	/usr/lib/golang/src/bytes/buffer.go:170 +0x78 fp=0xc00059f9d8 sp=0xc00059f9b0 pc=0xaaaaaae7cea840
bufio.(*Writer).Flush(0xc00059fa68)
	/usr/lib/golang/src/bufio/bufio.go:629 +0x64 fp=0xc00059fa18 sp=0xc00059f9d8 pc=0xaaaaaae7d0554c
encoding/csv.(*Writer).Flush(...)
	/usr/lib/golang/src/encoding/csv/writer.go:124
github.com/containers/podman/vendor/github.com/spf13/pflag.writeAsCSV({0xaaaaaae9ee0d20, 0x0, 0x0})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:38 +0xe0 fp=0xc00059faa8 sp=0xc00059fa18 pc=0xaaaaaae8124908
github.com/containers/podman/vendor/github.com/spf13/pflag.(*stringSliceValue).String(0xaaaaaae9eb0140?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:61 +0x3c fp=0xc00059fae8 sp=0xc00059faa8 pc=0xaaaaaae8124bfc
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarPF(0xaaaaaae8a4b4a8?, {0xaaaaaae918fce8, 0xc000314da0}, {0xaaaaaae8b391e5, 0x13}, {0x0, 0x0}, {0xaaaaaae8bb4907, 0x46})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:829 +0x94 fp=0xc00059fb28 sp=0xc00059fae8 pc=0xaaaaaae81186e4
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarP(...)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:837
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).StringSliceVar(0x0?, 0xaaaaaae9eb0a10, {0xaaaaaae8b391e5, 0x13}, {0xaaaaaae9ee0d20, 0x0, 0x0}, {0xaaaaaae8bb4907, 0x46})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:105 +0x120 fp=0xc00059fb80 sp=0xc00059fb28 pc=0xaaaaaae8125078
github.com/containers/podman/cmd/podman/common.DefineCreateFlags(0xaaaaaae9e0bd60?, 0xaaaaaae9eb09c0, 0x0)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/common/create.go:56 +0x1e4 fp=0xc00059fc68 sp=0xc00059fb80 pc=0xaaaaaae8a4b4fc
github.com/containers/podman/cmd/podman/containers.createFlags(0xaaaaaae8ff7100?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:71 +0x7c fp=0xc00059fcc0 sp=0xc00059fc68 pc=0xaaaaaae8a5bfac
github.com/containers/podman/cmd/podman/containers.init.6()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:99 +0x1ac fp=0xc00059fd20 sp=0xc00059fcc0 pc=0xaaaaaae8a5c204
runtime.doInit(0xaaaaaae9e57840)
	/usr/lib/golang/src/runtime/proc.go:6329 +0x134 fp=0xc00059fe50 sp=0xc00059fd20 pc=0xaaaaaae7c3608c
runtime.doInit(0xaaaaaae9e52c40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc00059ff80 sp=0xc00059fe50 pc=0xaaaaaae7c35fcc
runtime.main()
	/usr/lib/golang/src/runtime/proc.go:233 +0x1d0 fp=0xc00059ffd8 sp=0xc00059ff80 pc=0xaaaaaae7c287d0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00059ffd8 sp=0xc00059ffd8 pc=0xaaaaaae7c56694

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005efb0 sp=0xc00005ef98 pc=0xaaaaaae7c28c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.forcegchelper()
	/usr/lib/golang/src/runtime/proc.go:302 +0xb0 fp=0xc00005efd8 sp=0xc00005efb0 pc=0xaaaaaae7c28a90
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005efd8 sp=0xc00005efd8 pc=0xaaaaaae7c56694
created by runtime.init.5
	/usr/lib/golang/src/runtime/proc.go:290 +0x28

goroutine 18 [GC sweep wait]:
runtime.gopark(0x1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005a798 sp=0xc00005a780 pc=0xaaaaaae7c28c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.bgsweep(0x0?)
	/usr/lib/golang/src/runtime/mgcsweep.go:297 +0x114 fp=0xc00005a7c8 sp=0xc00005a798 pc=0xaaaaaae7c13c04
runtime.gcenable.func1()
	/usr/lib/golang/src/runtime/mgc.go:178 +0x2c fp=0xc00005a7d8 sp=0xc00005a7c8 pc=0xaaaaaae7c083d4
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005a7d8 sp=0xc00005a7d8 pc=0xaaaaaae7c56694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:178 +0x70

goroutine 19 [GC scavenge wait]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x412e848000000000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005af80 sp=0xc00005af68 pc=0xaaaaaae7c28c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.(*scavengerState).park(0xaaaaaae9eae6a0)
	/usr/lib/golang/src/runtime/mgcscavenge.go:389 +0x68 fp=0xc00005afa8 sp=0xc00005af80 pc=0xaaaaaae7c11b30
runtime.bgscavenge(0x0?)
	/usr/lib/golang/src/runtime/mgcscavenge.go:622 +0x6c fp=0xc00005afc8 sp=0xc00005afa8 pc=0xaaaaaae7c1209c
runtime.gcenable.func2()
	/usr/lib/golang/src/runtime/mgc.go:179 +0x2c fp=0xc00005afd8 sp=0xc00005afc8 pc=0xaaaaaae7c08374
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005afd8 sp=0xc00005afd8 pc=0xaaaaaae7c56694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:179 +0xb0

goroutine 20 [finalizer wait]:
runtime.gopark(0x3000?, 0x18000?, 0x0?, 0x30?, 0x3000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005e5a8 sp=0xc00005e590 pc=0xaaaaaae7c28c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.runfinq()
	/usr/lib/golang/src/runtime/mfinal.go:180 +0x110 fp=0xc00005e7d8 sp=0xc00005e5a8 pc=0xaaaaaae7c075c8
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005e7d8 sp=0xc00005e7d8 pc=0xaaaaaae7c56694
created by runtime.createfing
	/usr/lib/golang/src/runtime/mfinal.go:157 +0x64

goroutine 21 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005b748 sp=0xc00005b730 pc=0xaaaaaae7c28c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005b7d8 sp=0xc00005b748 pc=0xaaaaaae7c0a5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005b7d8 sp=0xc00005b7d8 pc=0xaaaaaae7c56694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 34 [GC worker (idle)]:
runtime.gopark(0x90f3ac90fa?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000506748 sp=0xc000506730 pc=0xaaaaaae7c28c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0005067d8 sp=0xc000506748 pc=0xaaaaaae7c0a5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0005067d8 sp=0xc0005067d8 pc=0xaaaaaae7c56694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 3 [GC worker (idle)]:
runtime.gopark(0xaaaaaae9180830?, 0xc0003889a0?, 0x18?, 0x14?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005f748 sp=0xc00005f730 pc=0xaaaaaae7c28c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005f7d8 sp=0xc00005f748 pc=0xaaaaaae7c0a5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005f7d8 sp=0xc00005f7d8 pc=0xaaaaaae7c56694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 22 [GC worker (idle)]:
runtime.gopark(0x90f3dfb364?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005bf48 sp=0xc00005bf30 pc=0xaaaaaae7c28c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005bfd8 sp=0xc00005bf48 pc=0xaaaaaae7c0a5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005bfd8 sp=0xc00005bfd8 pc=0xaaaaaae7c56694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 6 [chan receive]:
runtime.gopark(0x50000001000e68?, 0xaaaaaae7c2ef0c?, 0xd4?, 0x54?, 0xc000482b60?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc0000606d8 sp=0xc0000606c0 pc=0xaaaaaae7c28c08
runtime.chanrecv(0xc000498000, 0xc0000607b0, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:583 +0x498 fp=0xc000060768 sp=0xc0000606d8 pc=0xaaaaaae7bf5af0
runtime.chanrecv2(0x12a05f200?, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:447 +0x14 fp=0xc000060788 sp=0xc000060768 pc=0xaaaaaae7bf5644
github.com/containers/podman/vendor/k8s.io/klog/v2.(*loggingT).flushDaemon(0xc0000a4480?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:1169 +0x6c fp=0xc0000607c8 sp=0xc000060788 pc=0xaaaaaae86458b4
github.com/containers/podman/vendor/k8s.io/klog/v2.init.0.func1()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x2c fp=0xc0000607d8 sp=0xc0000607c8 pc=0xaaaaaae86436bc
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000607d8 sp=0xc0000607d8 pc=0xaaaaaae7c56694
created by github.com/containers/podman/vendor/k8s.io/klog/v2.init.0
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x124
+ SLEEP_WAIT 5 'podman load < ./test_file/vpn-server.tar'
+ wait_time=5
+ cmd='podman load < ./test_file/vpn-server.tar'
+ mode=1
+ python3 /root/mugen/libs/locallibs/sleep_wait.py --time 5 --cmd 'podman load < ./test_file/vpn-server.tar' --mode 1
runtime: lfstack.push invalid packing: node=0xffffffb310b520 cnt=0x1 packed=0xffffb310b5200001 -> node=0xffffb310b520
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaac2dd6310?, 0xaaaaaac1ed4f40?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffd0ec6818 sp=0xffffffd0ec67f0 pc=0xaaaaaac1ed01ec
runtime.(*lfstack).push(0xc000050f00?, 0xffffffb310b520)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffd0ec6848 sp=0xffffffd0ec6818 pc=0xaaaaaac1ea3d98
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaac4183ff8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffd0ec6878 sp=0xffffffd0ec6848 pc=0xaaaaaac1eca010
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffd0ec68b0 sp=0xffffffd0ec6878 pc=0xaaaaaac1ebda58
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffd0ec68b8 sp=0xffffffd0ec68b0 pc=0xaaaaaac1eb2908
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffd0ec68c0 sp=0xffffffd0ec68b8 pc=0xaaaaaac1efe484

goroutine 1 [running, locked to thread]:
runtime.systemstack_switch()
	/usr/lib/golang/src/runtime/asm_riscv64.s:96 +0x8 fp=0xc000527318 sp=0xc000527310 pc=0xaaaaaac1efe418
runtime.gcStart({0xffffffb30fc108?, 0xc000263a5d?, 0x310c90?})
	/usr/lib/golang/src/runtime/mgc.go:667 +0x358 fp=0xc0005273a8 sp=0xc000527318 pc=0xaaaaaac1eb2c80
runtime.mallocgc(0x1308, 0xaaaaaac32f06c0, 0x1)
	/usr/lib/golang/src/runtime/malloc.go:1148 +0x6a8 fp=0xc000527420 sp=0xc0005273a8 pc=0xaaaaaac1ea59b0
runtime.newobject(0xaaaaaac2e3b127?)
	/usr/lib/golang/src/runtime/malloc.go:1202 +0x38 fp=0xc000527440 sp=0xc000527420 pc=0xaaaaaac1ea5bd8
math/rand.NewSource(...)
	/usr/lib/golang/src/math/rand/rand.go:44
github.com/containers/podman/vendor/github.com/google/go-cmp/cmp.init()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/google/go-cmp/cmp/report_text.go:18 +0xa4 fp=0xc0005274d0 sp=0xc000527440 pc=0xaaaaaac28e783c
runtime.doInit(0xaaaaaac40ee340)
	/usr/lib/golang/src/runtime/proc.go:6329 +0x134 fp=0xc000527600 sp=0xc0005274d0 pc=0xaaaaaac1ee008c
runtime.doInit(0xaaaaaac40ebe40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527730 sp=0xc000527600 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40f5d20)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527860 sp=0xc000527730 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40ef400)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527990 sp=0xc000527860 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac4109380)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527ac0 sp=0xc000527990 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40f2400)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527bf0 sp=0xc000527ac0 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40f18c0)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527d20 sp=0xc000527bf0 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40f83c0)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527e50 sp=0xc000527d20 pc=0xaaaaaac1edffcc
runtime.doInit(0xaaaaaac40fcc40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc000527f80 sp=0xc000527e50 pc=0xaaaaaac1edffcc
runtime.main()
	/usr/lib/golang/src/runtime/proc.go:233 +0x1d0 fp=0xc000527fd8 sp=0xc000527f80 pc=0xaaaaaac1ed27d0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000527fd8 sp=0xc000527fd8 pc=0xaaaaaac1f00694

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005cfb0 sp=0xc00005cf98 pc=0xaaaaaac1ed2c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.forcegchelper()
	/usr/lib/golang/src/runtime/proc.go:302 +0xb0 fp=0xc00005cfd8 sp=0xc00005cfb0 pc=0xaaaaaac1ed2a90
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005cfd8 sp=0xc00005cfd8 pc=0xaaaaaac1f00694
created by runtime.init.5
	/usr/lib/golang/src/runtime/proc.go:290 +0x28

goroutine 18 [GC sweep wait]:
runtime.gopark(0x1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000058798 sp=0xc000058780 pc=0xaaaaaac1ed2c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.bgsweep(0x0?)
	/usr/lib/golang/src/runtime/mgcsweep.go:297 +0x114 fp=0xc0000587c8 sp=0xc000058798 pc=0xaaaaaac1ebdc04
runtime.gcenable.func1()
	/usr/lib/golang/src/runtime/mgc.go:178 +0x2c fp=0xc0000587d8 sp=0xc0000587c8 pc=0xaaaaaac1eb23d4
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000587d8 sp=0xc0000587d8 pc=0xaaaaaac1f00694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:178 +0x70

goroutine 19 [GC scavenge wait]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x412e848000000000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000058f80 sp=0xc000058f68 pc=0xaaaaaac1ed2c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.(*scavengerState).park(0xaaaaaac41586a0)
	/usr/lib/golang/src/runtime/mgcscavenge.go:389 +0x68 fp=0xc000058fa8 sp=0xc000058f80 pc=0xaaaaaac1ebbb30
runtime.bgscavenge(0x0?)
	/usr/lib/golang/src/runtime/mgcscavenge.go:622 +0x6c fp=0xc000058fc8 sp=0xc000058fa8 pc=0xaaaaaac1ebc09c
runtime.gcenable.func2()
	/usr/lib/golang/src/runtime/mgc.go:179 +0x2c fp=0xc000058fd8 sp=0xc000058fc8 pc=0xaaaaaac1eb2374
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000058fd8 sp=0xc000058fd8 pc=0xaaaaaac1f00694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:179 +0xb0

goroutine 20 [finalizer wait]:
runtime.gopark(0x3000?, 0x18000?, 0x0?, 0x30?, 0x3000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005c5a8 sp=0xc00005c590 pc=0xaaaaaac1ed2c08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.runfinq()
	/usr/lib/golang/src/runtime/mfinal.go:180 +0x110 fp=0xc00005c7d8 sp=0xc00005c5a8 pc=0xaaaaaac1eb15c8
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005c7d8 sp=0xc00005c7d8 pc=0xaaaaaac1f00694
created by runtime.createfing
	/usr/lib/golang/src/runtime/mfinal.go:157 +0x64

goroutine 21 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000059748 sp=0xc000059730 pc=0xaaaaaac1ed2c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0000597d8 sp=0xc000059748 pc=0xaaaaaac1eb45c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000597d8 sp=0xc0000597d8 pc=0xaaaaaac1f00694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 22 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000059f48 sp=0xc000059f30 pc=0xaaaaaac1ed2c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc000059fd8 sp=0xc000059f48 pc=0xaaaaaac1eb45c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000059fd8 sp=0xc000059fd8 pc=0xaaaaaac1f00694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 23 [GC worker (idle)]:
runtime.gopark(0x916c52f781?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005a748 sp=0xc00005a730 pc=0xaaaaaac1ed2c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005a7d8 sp=0xc00005a748 pc=0xaaaaaac1eb45c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005a7d8 sp=0xc00005a7d8 pc=0xaaaaaac1f00694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 24 [GC worker (idle)]:
runtime.gopark(0xaaaaaac342a830?, 0xc0003889e0?, 0x18?, 0x14?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005af48 sp=0xc00005af30 pc=0xaaaaaac1ed2c08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005afd8 sp=0xc00005af48 pc=0xaaaaaac1eb45c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005afd8 sp=0xc00005afd8 pc=0xaaaaaac1f00694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c
+ podman run -itd --name vpn --env-file ./test_file/vpn.env -p 700:700/udp -p 4700:4700/udp -d --privileged docker.io/hwdsl2/ipsec-vpn-server:latest
runtime: lfstack.push invalid packing: node=0xffffffbd266520 cnt=0x1 packed=0xffffbd2665200001 -> node=0xffffbd266520
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaae501f310?, 0xaaaaaae411df40?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffd7cc9728 sp=0xffffffd7cc9700 pc=0xaaaaaae41191ec
runtime.(*lfstack).push(0xc000052f00?, 0xffffffbd266520)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffd7cc9758 sp=0xffffffd7cc9728 pc=0xaaaaaae40ecd98
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaae63ccff8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffd7cc9788 sp=0xffffffd7cc9758 pc=0xaaaaaae4113010
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffd7cc97c0 sp=0xffffffd7cc9788 pc=0xaaaaaae4106a58
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffd7cc97c8 sp=0xffffffd7cc97c0 pc=0xaaaaaae40fb908
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffd7cc97d0 sp=0xffffffd7cc97c8 pc=0xaaaaaae4147484

goroutine 1 [running, locked to thread]:
runtime.systemstack_switch()
	/usr/lib/golang/src/runtime/asm_riscv64.s:96 +0x8 fp=0xc00059f8f0 sp=0xc00059f8e8 pc=0xaaaaaae4147418
runtime.gcStart({0xffffffbd257108?, 0x59?, 0xe40ee7e0?})
	/usr/lib/golang/src/runtime/mgc.go:667 +0x358 fp=0xc00059f980 sp=0xc00059f8f0 pc=0xaaaaaae40fbc80
runtime.mallocgc(0x1000, 0xaaaaaae53fa240, 0x1)
	/usr/lib/golang/src/runtime/malloc.go:1148 +0x6a8 fp=0xc00059f9f8 sp=0xc00059f980 pc=0xaaaaaae40ee9b0
runtime.makeslice(0x3000?, 0x3000?, 0x747400c0002f7f55?)
	/usr/lib/golang/src/runtime/slice.go:103 +0x70 fp=0xc00059fa18 sp=0xc00059f9f8 pc=0xaaaaaae41314c0
bufio.NewWriterSize(...)
	/usr/lib/golang/src/bufio/bufio.go:593
bufio.NewWriter(...)
	/usr/lib/golang/src/bufio/bufio.go:602
encoding/csv.NewWriter(...)
	/usr/lib/golang/src/encoding/csv/writer.go:40
github.com/containers/podman/vendor/github.com/spf13/pflag.writeAsCSV({0xc000316420, 0x1, 0x1})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:33 +0x70 fp=0xc00059faa8 sp=0xc00059fa18 pc=0xaaaaaae4617898
github.com/containers/podman/vendor/github.com/spf13/pflag.(*stringSliceValue).String(0xaaaaaae63a3140?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:61 +0x3c fp=0xc00059fae8 sp=0xc00059faa8 pc=0xaaaaaae4617bfc
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarPF(0xaaaaaae4f3fdb4?, {0xaaaaaae5682ce8, 0xc000316f00}, {0xaaaaaae5014be5, 0x6}, {0x0, 0x0}, {0xaaaaaae5022544, 0xe})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:829 +0x94 fp=0xc00059fb28 sp=0xc00059fae8 pc=0xaaaaaae460b6e4
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).VarP(...)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/flag.go:837
github.com/containers/podman/vendor/github.com/spf13/pflag.(*FlagSet).StringSliceVar(0x0?, 0xaaaaaae63a3fa8, {0xaaaaaae5014be5, 0x6}, {0xc000316420, 0x1, 0x1}, {0xaaaaaae5022544, 0xe})
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/github.com/spf13/pflag/string_slice.go:105 +0x120 fp=0xc00059fb80 sp=0xc00059fb28 pc=0xaaaaaae4618078
github.com/containers/podman/cmd/podman/common.DefineCreateFlags(0xaaaaaae62fed60?, 0xaaaaaae63a39c0, 0x0)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/common/create.go:647 +0x1b20 fp=0xc00059fc68 sp=0xc00059fb80 pc=0xaaaaaae4f3fe38
github.com/containers/podman/cmd/podman/containers.createFlags(0xaaaaaae54ea100?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:71 +0x7c fp=0xc00059fcc0 sp=0xc00059fc68 pc=0xaaaaaae4f4efac
github.com/containers/podman/cmd/podman/containers.init.6()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/cmd/podman/containers/create.go:99 +0x1ac fp=0xc00059fd20 sp=0xc00059fcc0 pc=0xaaaaaae4f4f204
runtime.doInit(0xaaaaaae634a840)
	/usr/lib/golang/src/runtime/proc.go:6329 +0x134 fp=0xc00059fe50 sp=0xc00059fd20 pc=0xaaaaaae412908c
runtime.doInit(0xaaaaaae6345c40)
	/usr/lib/golang/src/runtime/proc.go:6306 +0x74 fp=0xc00059ff80 sp=0xc00059fe50 pc=0xaaaaaae4128fcc
runtime.main()
	/usr/lib/golang/src/runtime/proc.go:233 +0x1d0 fp=0xc00059ffd8 sp=0xc00059ff80 pc=0xaaaaaae411b7d0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00059ffd8 sp=0xc00059ffd8 pc=0xaaaaaae4149694

goroutine 2 [force gc (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005efb0 sp=0xc00005ef98 pc=0xaaaaaae411bc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.forcegchelper()
	/usr/lib/golang/src/runtime/proc.go:302 +0xb0 fp=0xc00005efd8 sp=0xc00005efb0 pc=0xaaaaaae411ba90
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005efd8 sp=0xc00005efd8 pc=0xaaaaaae4149694
created by runtime.init.5
	/usr/lib/golang/src/runtime/proc.go:290 +0x28

goroutine 18 [GC sweep wait]:
runtime.gopark(0x1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005a798 sp=0xc00005a780 pc=0xaaaaaae411bc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.bgsweep(0x0?)
	/usr/lib/golang/src/runtime/mgcsweep.go:297 +0x114 fp=0xc00005a7c8 sp=0xc00005a798 pc=0xaaaaaae4106c04
runtime.gcenable.func1()
	/usr/lib/golang/src/runtime/mgc.go:178 +0x2c fp=0xc00005a7d8 sp=0xc00005a7c8 pc=0xaaaaaae40fb3d4
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005a7d8 sp=0xc00005a7d8 pc=0xaaaaaae4149694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:178 +0x70

goroutine 19 [GC scavenge wait]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x412e848000000000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005af80 sp=0xc00005af68 pc=0xaaaaaae411bc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.(*scavengerState).park(0xaaaaaae63a16a0)
	/usr/lib/golang/src/runtime/mgcscavenge.go:389 +0x68 fp=0xc00005afa8 sp=0xc00005af80 pc=0xaaaaaae4104b30
runtime.bgscavenge(0x0?)
	/usr/lib/golang/src/runtime/mgcscavenge.go:622 +0x6c fp=0xc00005afc8 sp=0xc00005afa8 pc=0xaaaaaae410509c
runtime.gcenable.func2()
	/usr/lib/golang/src/runtime/mgc.go:179 +0x2c fp=0xc00005afd8 sp=0xc00005afc8 pc=0xaaaaaae40fb374
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005afd8 sp=0xc00005afd8 pc=0xaaaaaae4149694
created by runtime.gcenable
	/usr/lib/golang/src/runtime/mgc.go:179 +0xb0

goroutine 20 [finalizer wait]:
runtime.gopark(0x3000?, 0x18000?, 0x0?, 0x30?, 0x3000?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005e5a8 sp=0xc00005e590 pc=0xaaaaaae411bc08
runtime.goparkunlock(...)
	/usr/lib/golang/src/runtime/proc.go:369
runtime.runfinq()
	/usr/lib/golang/src/runtime/mfinal.go:180 +0x110 fp=0xc00005e7d8 sp=0xc00005e5a8 pc=0xaaaaaae40fa5c8
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005e7d8 sp=0xc00005e7d8 pc=0xaaaaaae4149694
created by runtime.createfing
	/usr/lib/golang/src/runtime/mfinal.go:157 +0x64

goroutine 21 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005b748 sp=0xc00005b730 pc=0xaaaaaae411bc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005b7d8 sp=0xc00005b748 pc=0xaaaaaae40fd5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005b7d8 sp=0xc00005b7d8 pc=0xaaaaaae4149694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 3 [GC worker (idle)]:
runtime.gopark(0x0?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005f748 sp=0xc00005f730 pc=0xaaaaaae411bc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005f7d8 sp=0xc00005f748 pc=0xaaaaaae40fd5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005f7d8 sp=0xc00005f7d8 pc=0xaaaaaae4149694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 4 [GC worker (idle)]:
runtime.gopark(0x91a978b7f7?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc00005ff48 sp=0xc00005ff30 pc=0xaaaaaae411bc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc00005ffd8 sp=0xc00005ff48 pc=0xaaaaaae40fd5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc00005ffd8 sp=0xc00005ffd8 pc=0xaaaaaae4149694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 5 [GC worker (idle)]:
runtime.gopark(0x91a97681f1?, 0x0?, 0x0?, 0x0?, 0x0?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000060748 sp=0xc000060730 pc=0xaaaaaae411bc08
runtime.gcBgMarkWorker()
	/usr/lib/golang/src/runtime/mgc.go:1235 +0x100 fp=0xc0000607d8 sp=0xc000060748 pc=0xaaaaaae40fd5c0
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc0000607d8 sp=0xc0000607d8 pc=0xaaaaaae4149694
created by runtime.gcBgMarkStartWorkers
	/usr/lib/golang/src/runtime/mgc.go:1159 +0x2c

goroutine 8 [chan receive]:
runtime.gopark(0xc000500000?, 0xaaaaaae4121f0c?, 0x0?, 0x0?, 0xc000502401?)
	/usr/lib/golang/src/runtime/proc.go:363 +0x110 fp=0xc000060ed8 sp=0xc000060ec0 pc=0xaaaaaae411bc08
runtime.chanrecv(0xc000474000, 0xc000060fb0, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:583 +0x498 fp=0xc000060f68 sp=0xc000060ed8 pc=0xaaaaaae40e8af0
runtime.chanrecv2(0x12a05f200?, 0x0?)
	/usr/lib/golang/src/runtime/chan.go:447 +0x14 fp=0xc000060f88 sp=0xc000060f68 pc=0xaaaaaae40e8644
github.com/containers/podman/vendor/k8s.io/klog/v2.(*loggingT).flushDaemon(0xc0000a44e0?)
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:1169 +0x6c fp=0xc000060fc8 sp=0xc000060f88 pc=0xaaaaaae4b388b4
github.com/containers/podman/vendor/k8s.io/klog/v2.init.0.func1()
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x2c fp=0xc000060fd8 sp=0xc000060fc8 pc=0xaaaaaae4b366bc
runtime.goexit()
	/usr/lib/golang/src/runtime/asm_riscv64.s:516 +0x4 fp=0xc000060fd8 sp=0xc000060fd8 pc=0xaaaaaae4149694
created by github.com/containers/podman/vendor/k8s.io/klog/v2.init.0
	/home/abuild/rpmbuild/BUILD/podman-3.4.4/_build/src/github.com/containers/podman/vendor/k8s.io/klog/v2/klog.go:420 +0x124
```

x86在加载pki时出错，对应log如下

```
+ strongswan pki
unable to set OpenSSL FIPS mode(2) from (0)
plugin 'openssl': failed to load - openssl_plugin_create returned NULL
+ grep 'strongSwan 5.7.2 PKI tool' strongswan_test_pki.log
+ CHECK_RESULT 1 0 0 'Failed to check the pki'
```

