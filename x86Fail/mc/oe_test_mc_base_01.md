# oe_test_mc_base_01

测试套问题， x86 和 riscv 错误原因一致

测试套尝试 grep 中文字串， Line 41

```
mc -F 2>&1 | grep 'Home路径'
```

实际输出如下

```
# mc -F 
Home directory: /root
Profile root directory: /root

[System data]
    Config directory: /etc/mc/
    Data directory:   /usr/share/mc/
    File extension handlers: /usr/libexec/mc/ext.d/
    VFS plugins and scripts: /usr/libexec/mc/
        extfs.d:        /usr/libexec/mc/extfs.d/
        fish:           /usr/libexec/mc/fish/

[User data]
    Config directory: /root/.config/mc/
    Data directory:   /root/.local/share/mc/
        skins:          /root/.local/share/mc/skins/
        extfs.d:        /root/.local/share/mc/extfs.d/
        fish:           /root/.local/share/mc/fish/
        mcedit macros:  /root/.local/share/mc/mc.macros
        mcedit external macros: /root/.local/share/mc/mcedit/macros.d/macro.*
    Cache directory:  /root/.cache/mc/
```

