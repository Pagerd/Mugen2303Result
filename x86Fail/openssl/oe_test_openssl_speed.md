# oe_test_openssl_speed

测试套问题，x86 和 riscv 错误原因一致

错误来自 Line 26-28 和 Line 32-34

```
    openssl speed -elapsed aes-128-cbc >> openssl.log
    grep "aes-128 cbc"  openssl.log
    CHECK_RESULT $? 0 0 "aes-128-cbc encryption and decryption operation speed fail"

    openssl speed -elapsed -evp sm4 >> openssl.log
    grep "sm4-cbc" openssl.log
    CHECK_RESULT $? 0 0 "sm4 encryption and decryption operation speed fail"
```

grep 所示字串和实际不符

示例 openssl.log

```
version: 3.0.8
built on: Thu Mar 23 13:01:03 2023 UTC
options: bn(64,64)
compiler: gcc -fPIC -pthread -Wall -O3 -O2 -g -pipe -Wall -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -Wp,-D_GLIBCXX_ASSERTIONS -fstack-protector-strong -grecord-gcc-switches -specs=/usr/lib/rpm/generic-hardened-cc1 -fasynchronous-unwind-tables -fstack-clash-protection -Wa,--noexecstack -Wa,--generate-missing-build-notes=yes -specs=/usr/lib/rpm/generic-hardened-ld -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_BUILDING_OPENSSL -DZLIB -DNDEBUG -DPURIFY -DDEVRANDOM="\"/dev/urandom\""
CPUINFO: N/A
The 'numbers' are in 1000s of bytes per second processed.
type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
SM4-CBC          16805.02k    26331.54k    30719.83k    31978.06k    32011.61k    31390.87k

version: 3.0.8
built on: Thu Mar 23 13:01:03 2023 UTC
options: bn(64,64)
compiler: gcc -fPIC -pthread -Wall -O3 -O2 -g -pipe -Wall -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -Wp,-D_GLIBCXX_ASSERTIONS -fstack-protector-strong -grecord-gcc-switches -specs=/usr/lib/rpm/generic-hardened-cc1 -fasynchronous-unwind-tables -fstack-clash-protection -Wa,--noexecstack -Wa,--generate-missing-build-notes=yes -specs=/usr/lib/rpm/generic-hardened-ld -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_BUILDING_OPENSSL -DZLIB -DNDEBUG -DPURIFY -DDEVRANDOM="\"/dev/urandom\""
CPUINFO: N/A
The 'numbers' are in 1000s of bytes per second processed.
type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
aes-128-cbc      15303.56k    14109.76k    15346.60k    15833.56k    16031.74k    15943.10k
```

