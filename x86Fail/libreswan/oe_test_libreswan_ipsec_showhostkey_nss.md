# oe_test_libreswan_ipsec_showhostkey_nss

x86 和 riscv 失败原因一致

测试套 Line 26-27

```
    ipsec rsasigkey &> getkey
    ckaid=$(tail -n 1 getkey | awk '{print $12}')
```

得到 ``ckaid`` 为空

```
+ ipsec rsasigkey
++ tail -n 1 getkey
++ awk '{print $12}'
+ ckaid=

+ ipsec showhostkey --dump
ipsec showhostkey: authentication of "NSS Certificate DB" failed
FATAL ERROR: ipsec showhostkey: NSS: could not authenticate slot

+ ipsec showhostkey --list
ipsec showhostkey: authentication of "NSS Certificate DB" failed
FATAL ERROR: ipsec showhostkey: NSS: could not authenticate slot

+ ipsec showhostkey --left --ckaid --nssdir /var/lib/ipsec/nss
ipsec showhostkey: authentication of "NSS Certificate DB" failed
FATAL ERROR: ipsec showhostkey: NSS: could not authenticate slot

+ ipsec showhostkey --ipseckey --ckaid
/usr/libexec/ipsec/showhostkey: option '--ckaid' requires an argument
Usage: showhostkey [ --verbose ] [ --debug ]
        { --version | --dump | --list | --left | --right |
                --ipseckey [ --precedence <precedence> ] 
                [ --gateway <gateway> ] }
        [ --rsaid <rsaid> | --ckaid <ckaid> ]
        [ --nssdir <nssdir> ] [ --password <password> ]
```

