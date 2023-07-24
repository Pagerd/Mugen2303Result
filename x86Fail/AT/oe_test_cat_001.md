### oe_test_cat_001

当前版本的openEuler（6.1.19-7.0.0.17.oe2303.x86_64和6.1.8-3.oe2303.riscv64）root用户的User ID Info是Super User而不是root，所以/etc/passwd中root的信息为`root:x:0:0:Super User:/root:/bin/bash`而不是`root:x:0:0:root:/root:/bin/bash`，导致grep失败