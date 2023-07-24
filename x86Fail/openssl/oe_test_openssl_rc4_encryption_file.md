# oe_test_openssl_rc4_encryption_file

x86 和 riscv 报错一致

```
+ expect
spawn openssl enc -e -rc4 -in 1.key -out 1.key.enc
enter RC4 encryption password:
Verifying - enter RC4 encryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
Error setting cipher RC4
40BC206A6E7F0000:error:0308010C:digital envelope routines:inner_evp_generic_fetch:unsupported:crypto/evp/evp_fetch.c:373:Global default library context, Algorithm (RC4 : 40), Properties ()

+ expect
spawn openssl enc -d -rc4 -in 1.key.enc -out 1.key.dec
enter RC4 decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
Error setting cipher RC4
40FC25EC697F0000:error:0308010C:digital envelope routines:inner_evp_generic_fetch:unsupported:crypto/evp/evp_fetch.c:373:Global default library context, Algorithm (RC4 : 40), Properties ()
```

