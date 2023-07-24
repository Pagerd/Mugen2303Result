### groovy

缺少对应的软件包,log报错如下所示

```
 DNF_INSTALL 'groovy18 tar'
+ pkgs='groovy18 tar'
+ node=1
+ '[' -z '' ']'
+ tmpfile=
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs 'groovy18 tar' --node 1 --tempfile ''
+ tmpfile2='Last metadata expiration check: 0:08:31 ago on Mon 26 Jun 2023 01:57:00 AM CST.
Package tar-2:1.34-4.oe2303.riscv64 is already installed.
Error: 
 Problem: package groovy18-1.8.9-1.oe2303.noarch requires mvn(org.codehaus.gpars:gpars), but none of the providers can be installed
  - package gpars-1.2.1-13.oe2303.noarch requires mvn(org.codehaus.groovy:groovy-all), but none of the providers can be installed
  - conflicting requests
  - nothing provides mvn(jline:jline) needed by groovy-2.4.8-11.oe2303.noarch
(try to add '\''--skip-broken'\'' to skip uninstallable packages or '\''--nobest'\'' to use not only best candidate packages)'
+ '[' -z '' ']'
+ tmpfile='Last metadata expiration check: 0:08:31 ago on Mon 26 Jun 2023 01:57:00 AM CST.
Package tar-2:1.34-4.oe2303.riscv64 is already installed.
Error: 
 Problem: package groovy18-1.8.9-1.oe2303.noarch requires mvn(org.codehaus.gpars:gpars), but none of the providers can be installed
  - package gpars-1.2.1-13.oe2303.noarch requires mvn(org.codehaus.groovy:groovy-all), but none of the providers can be installed
  - conflicting requests
  - nothing provides mvn(jline:jline) needed by groovy-2.4.8-11.oe2303.noarch
(try to add '\''--skip-broken'\'' to skip uninstallable packages or '\''--nobest'\'' to use not only best candidate packages)'
```

