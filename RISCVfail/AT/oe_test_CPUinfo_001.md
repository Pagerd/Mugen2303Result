### oe_test_CPUinfo_001

risc-v架构的openeuler的`lscpu`命令输出格式和x86_64架构的不太一样，risc-v：

```
[root@openeuler-riscv64 ~]# lscpu
架构：            riscv64
  字节序：        Little Endian
CPU:              8
  在线 CPU 列表： 0-7
```

X86_64:

```
[root@localhost ~]# lscpu
Architecture:            x86_64
  CPU op-mode(s):        32-bit, 64-bit
  Address sizes:         40 bits physical, 48 bits virtual
  Byte Order:            Little Endian
CPU(s):                  8
  On-line CPU(s) list:   0-7
Vendor ID:               AuthenticAMD
  BIOS Vendor ID:        QEMU
  Model name:            QEMU Virtual CPU version 2.5+
    BIOS Model name:     pc-i440fx-8.0
    CPU family:          15
    Model:               107
    Thread(s) per core:  1
    Core(s) per socket:  8
    Socket(s):           1
    Stepping:            1
    BogoMIPS:            2000.02
    Flags:               fpu de pse tsc msr pae mce cx8 apic sep mtrr pge mca cm
                         ov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx lm
                          rep_good nopl cpuid extd_apicid pni cx16 hypervisor la
                         hf_lm cmp_legacy svm 3dnowprefetch vmmcall
Virtualization features:
  Virtualization:        AMD-V
Caches (sum of all):
  L1d:                   512 KiB (8 instances)
  L1i:                   512 KiB (8 instances)
  L2:                    4 MiB (8 instances)
  L3:                    128 MiB (8 instances)
NUMA:
  NUMA node(s):          1
  NUMA node0 CPU(s):     0-7
Vulnerabilities:
  Itlb multihit:         Not affected
  L1tf:                  Not affected
  Mds:                   Not affected
  Meltdown:              Not affected
  Mmio stale data:       Not affected
  Retbleed:              Not affected
  Spec store bypass:     Not affected
  Spectre v1:            Mitigation; usercopy/swapgs barriers and __user pointer
                          sanitization
  Spectre v2:            Mitigation; Retpolines, STIBP disabled, RSB filling, PB
                         RSB-eIBRS Not affected
  Srbds:                 Not affected
  Tsx async abort:       Not affected
```

这两种架构下`lshw `命令的输出格式也不一样，以产看cpu为例，risc-v:

```
[root@openeuler-riscv64 ~]# lshw -c cpu
  *-cpu:0
       description: CPU
       product: cpu
       physical id: 0
       bus info: cpu@0
       width: 32 bits
  *-cpu:1
       description: CPU
       product: cpu
       physical id: 1
       bus info: cpu@1
       width: 32 bits
  *-cpu:2
       description: CPU
       product: cpu
       physical id: 2
       bus info: cpu@2
       width: 32 bits
  *-cpu:3
       description: CPU
       product: cpu
       physical id: 3
       bus info: cpu@3
       width: 32 bits
  *-cpu:4
       description: CPU
       product: cpu
       physical id: 4
       bus info: cpu@4
       width: 32 bits
  *-cpu:5
       description: CPU
       product: cpu
       physical id: 5
       bus info: cpu@5
       width: 32 bits
  *-cpu:6
       description: CPU
       product: cpu
       physical id: 6
       bus info: cpu@6
       width: 32 bits
  *-cpu:7
       description: CPU
       product: cpu
       physical id: 7
       bus info: cpu@7
       width: 32 bits
  *-cpu:8 DISABLED
       description: CPU
       product: cpu-map
       physical id: 8
       bus info: cpu@8
```



X86_64:

```
[root@localhost ~]# lshw -c cpu
  *-cpu
       description: CPU
       product: QEMU Virtual CPU version 2.5+
       vendor: Advanced Micro Devices [AMD]
       physical id: 400
       bus info: cpu@0
       version: pc-i440fx-8.0
       slot: CPU 0
       size: 2GHz
       capacity: 2GHz
       width: 64 bits
       capabilities: fpu fpu_exception wp de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx x86-64 rep_good nopl cpuid extd_apicid pl
       configuration: cores=8 enabledcores=8 threads=1
```



所以测试脚本里的命令并不适用risc-v架构下的openeuler