# oe_test_freeradius_freeradius-utils_radsqlrelay

x86 和 riscv 失败原因一致

测试需要安装 mysql5 mysql5-server 软件包，但是这两个软件包不存在，导致依赖的 mysql 无法安装

```
++ python3 /root/mugen/libs/locallibs/rpm_manage.py install --pkgs 'freeradius freeradius-utils perl-DBD-MySQL mysql5 mysql5-server freeradius-mysql' --node 1 --tempfile ''
Fri May 26 18:54:02 2023 - ERROR - pkgs:(mysql5 mysql5-server) not found

+ radsqlrelay -1 -d mysql -b radius -h localhost -p Test123 -u root /tmp/radius.sql
install_driver(mysql) failed: Can't locate DBD/mysql.pm in @INC (you may need to install the DBD::mysql module) (@INC contains: /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5) at (eval 8) line 3.
Perhaps the DBD::mysql perl module hasn't been fully installed,
or perhaps the capitalisation of 'mysql' isn't right.
Available drivers: DBM, ExampleP, File, Gofer, Mem, Sponge.
 at /usr/bin/radsqlrelay line 149.
+ mysql -uroot -pTest123 -e 'use radius;
                               select * from radcheck where username='\''wjf'\'';
    '
+ grep wjf
oe_test_freeradius_freeradius-utils_radsqlrelay.sh: line 50: mysql: command not found

+ radsqlrelay -1 -d mysql -b radius -h localhost -f /tmp/passwdfile.txt -u root /tmp/radius.sql
install_driver(mysql) failed: Can't locate DBD/mysql.pm in @INC (you may need to install the DBD::mysql module) (@INC contains: /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5) at (eval 8) line 3.
Perhaps the DBD::mysql perl module hasn't been fully installed,
or perhaps the capitalisation of 'mysql' isn't right.
Available drivers: DBM, ExampleP, File, Gofer, Mem, Sponge.
 at /usr/bin/radsqlrelay line 149.
+ mysql -uroot -pTest123 -e 'use radius;
                               select * from radcheck where username='\''wjf'\'';
    '
+ grep wjf
oe_test_freeradius_freeradius-utils_radsqlrelay.sh: line 60: mysql: command not found

+ radsqlrelay -1 -d mysql -b radius -h 127.0.0.1 -p Test123 -u root -P 3306 /tmp/radius.sql
install_driver(mysql) failed: Can't locate DBD/mysql.pm in @INC (you may need to install the DBD::mysql module) (@INC contains: /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5) at (eval 8) line 3.
Perhaps the DBD::mysql perl module hasn't been fully installed,
or perhaps the capitalisation of 'mysql' isn't right.
Available drivers: DBM, ExampleP, File, Gofer, Mem, Sponge.
 at /usr/bin/radsqlrelay line 149.
+ mysql -uroot -pTest123 -e 'use radius;
                               select * from radcheck where username='\''wjf'\'';
    '
+ grep wjf
oe_test_freeradius_freeradius-utils_radsqlrelay.sh: line 69: mysql: command not found
```

