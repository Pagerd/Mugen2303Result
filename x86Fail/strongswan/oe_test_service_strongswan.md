### oe_test_service_strongswan:服务启动失败：没有对应文件

riscv与x86报错相同

x86报错内容为

```
+ systemctl disable strongswan.service
Removed /etc/systemd/system/multi-user.target.wants/strongswan.service.
Removed /etc/systemd/system/strongswan-swanctl.service.
+ find /etc/systemd/system/strongswan-swanctl.service /etc/systemd/system/multi-user.target.wants/strongswan.service
find: ‘/etc/systemd/system/strongswan-swanctl.service’: No such file or directory
find: ‘/etc/systemd/system/multi-user.target.wants/strongswan.service’: No such file or directory
+ CHECK_RESULT 1 0 1 'strongswan.service disable failed'
```

而riscv有更详细的报错log

```
Apr 27 03:23:46 openeuler-riscv64 charon-systemd[1398]: PKCS11 module '<name>' lacks library path
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: OpenSSL FIPS mode(2) - enabled
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: failed to open /dev/net/tun: No such file or directory
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: failed to create TUN device
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: plugin 'kernel-libipsec': failed to load - kernel_libipsec_plugin_create returned NULL
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: received netlink error: Operation not supported (95)
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: unable to create IPv4 routing table rule
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: received netlink error: Operation not supported (95)
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: unable to create IPv6 routing table rule
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading ca certificates from '/etc/strongswan/ipsec.d/cacerts'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading aa certificates from '/etc/strongswan/ipsec.d/aacerts'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading ocsp signer certificates from '/etc/strongswan/ipsec.d/ocspcerts'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading attribute certificates from '/etc/strongswan/ipsec.d/acerts'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading crls from '/etc/strongswan/ipsec.d/crls'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading secrets from '/etc/strongswan/ipsec.secrets'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: sql plugin: database URI not set
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: opening triplet file /etc/strongswan/ipsec.d/triplets.dat failed: No such file or directory
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loaded 0 RADIUS server configurations
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: MAP server certificate not defined
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: TNC recommendation policy is 'default'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading IMVs from '/etc/tnc_config'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: opening configuration file '/etc/tnc_config' failed: No such file or directory
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: missing PDP server name, PDP disabled
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loading IMCs from '/etc/tnc_config'
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: opening configuration file '/etc/tnc_config' failed: No such file or directory
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: HA config misses local/remote address
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: no script for ext-auth script defined, disabled
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: loaded plugins: charon-systemd pkcs11 tpm aes des rc2 sha2 sha1 md4 md5 mgf1 random nonce x509 revocation constraints acert pubkey pkcs1 pkcs7 pkcs12 pgp dnskey sshkey pem openssl gcrypt pkcs8 fips-prf gmp curve25519 chapoly xcbc cmac hmac kdf ctr ccm gcm drbg newhope curl sqlite attr kernel-netlink resolve socket-default farp stroke vici updown eap-identity eap-sim eap-aka eap-aka-3gpp eap-aka-3gpp2 eap-md5 eap-gtc eap-mschapv2 eap-dynamic eap-radius eap-tls eap-ttls eap-peap eap-tnc xauth-generic xauth-eap xauth-pam xauth-noauth tnc-imc tnc-imv tnc-tnccs tnccs-20 tnccs-11 tnccs-dynamic dhcp led duplicheck unity counters
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: spawning 16 worker threads
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: thread 5 received 11
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: thread 6 received 11
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]: thread 7 received 11
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]:  dumping 7 stack frame addresses:
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]:  dumping 7 stack frame addresses:
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]:   linux-vdso.so.1 @ 0xffffff8d60a000 (__vdso_rt_sigreturn+0x0) [0xffffff8d60a800]
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1398]:   linux-vdso.so.1 @ 0xffffff8d60a000 (__vdso_rt_sigreturn+0x0) [0xffffff8d60a800]
Apr 27 03:23:47 openeuler-riscv64 charon-systemd[1417]: addr2line: 'linux-vdso.so.1': No such file
Apr 27 03:23:47 openeuler-riscv64 systemd[1]: Started Process Core Dump (PID 1418/UID 0).
░░ Subject: A start job for unit systemd-coredump@45-1418-0.service has finished successfully
```

