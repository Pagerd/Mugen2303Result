### oe_test_rpm_suffix_name

部分dnf源中的包的后缀（Release字段）为oe2而不是oe2303。不过看上去都像是测试用的包。

```
[root@openeuler-riscv64 mugen]# dnf list |grep -wv oe2303 | grep -v 'Packages\|Last metadata expiration check'
helloworld.riscv64                                      1.0-1.oe2                                         oetestsuite
helloworld-debuginfo.riscv64                            1.0-1.oe2                                         oetestsuite
helloworld-debugsource.riscv64                          1.0-1.oe2                                         oetestsuite
oetestsuite.noarch                                      0.1-2.oe2                                         oetestsuite
```

### 