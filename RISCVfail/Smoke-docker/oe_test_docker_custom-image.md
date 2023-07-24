#### oe_test_docker_custom-image

打包构建时出错

```
+ docker build -t new_euler:v1.0 .
runtime: lfstack.push invalid packing: node=0xffffff72b3e9c0 cnt=0x1 packed=0xffff72b3e9c00001 -> node=0xffff72b3e9c0
fatal error: lfstack.push

runtime stack:
runtime.throw({0xaaaaaac2e15b3e?, 0xaaaaaac1f8c078?})
	/usr/lib/golang/src/runtime/panic.go:1047 +0x44 fp=0xffffffd2a0c7c8 sp=0xffffffd2a0c7a0 pc=0xaaaaaac1f87324
runtime.(*lfstack).push(0xc00004e500?, 0xffffff72b3e9c0)
	/usr/lib/golang/src/runtime/lfstack.go:30 +0x120 fp=0xffffffd2a0c7f8 sp=0xffffffd2a0c7c8 pc=0xaaaaaac1f5b430
runtime.(*spanSetBlockAlloc).free(...)
	/usr/lib/golang/src/runtime/mspanset.go:292
runtime.(*spanSet).reset(0xaaaaaac40b9cf8)
	/usr/lib/golang/src/runtime/mspanset.go:265 +0xb0 fp=0xffffffd2a0c828 sp=0xffffffd2a0c7f8 pc=0xaaaaaac1f81148
runtime.finishsweep_m()
	/usr/lib/golang/src/runtime/mgcsweep.go:260 +0xc0 fp=0xffffffd2a0c860 sp=0xffffffd2a0c828 pc=0xaaaaaac1f75168
runtime.gcStart.func1()
	/usr/lib/golang/src/runtime/mgc.go:668 +0x20 fp=0xffffffd2a0c868 sp=0xffffffd2a0c860 pc=0xaaaaaac1f6a018
runtime.systemstack()
	/usr/lib/golang/src/runtime/asm_riscv64.s:133 +0x54 fp=0xffffffd2a0c870 sp=0xffffffd2a0c868 pc=0xaaaaaac1fb3f2c

```

