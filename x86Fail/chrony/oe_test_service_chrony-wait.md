# oe_test_service_chrony-wait

测试套问题， x86 和 riscv 错误原因一致

测试依赖 chrony 软件包但是该软件包在 x86 和 riscv 均没有预装

```
+ P_SSH_CMD --cmd 'cp /etc/chrony.conf /etc/chrony.conf_bak;sed -i '\''s/^pool/#pool/'\'' /etc/chrony.conf;sed -i '\''s/^#allow.*/allow all/'\'' /etc/chrony.conf;sed -i '\''s/^#local.*/local/'\'' /etc/chrony.conf;systemctl restart chronyd.service;systemctl stop firewalld.service' --node 2
+ python3 /root/mugen/libs/locallibs/ssh_cmd.py --cmd 'cp /etc/chrony.conf /etc/chrony.conf_bak;sed -i '\''s/^pool/#pool/'\'' /etc/chrony.conf;sed -i '\''s/^#allow.*/allow all/'\'' /etc/chrony.conf;sed -i '\''s/^#local.*/local/'\'' /etc/chrony.conf;systemctl restart chronyd.service;systemctl stop firewalld.service' --node 2
cp: cannot stat '/etc/chrony.conf': No such file or directory
sed: can't read /etc/chrony.conf: No such file or directory
sed: can't read /etc/chrony.conf: No such file or directory
sed: can't read /etc/chrony.conf: No such file or directory
Failed to restart chronyd.service: Unit chronyd.service not found.
Failed to stop firewalld.service: Unit firewalld.service not loaded.
+ cp /etc/chrony.conf /etc/chrony.conf_bak
cp: cannot stat '/etc/chrony.conf': No such file or directory
+ sed -i 's/^pool.*/server 10.0.0.4 iburst minpoll 3 maxpoll 3/' /etc/chrony.conf
sed: can't read /etc/chrony.conf: No such file or directory
+ sed -i 's/^#allow.*/allow all/' /etc/chrony.conf
sed: can't read /etc/chrony.conf: No such file or directory
+ sed -i 's/^#local/local/' /etc/chrony.conf
sed: can't read /etc/chrony.conf: No such file or directory
+ systemctl restart chronyd.service
Failed to restart chronyd.service: Unit chronyd.service not found.

+ systemctl restart chrony-wait.service
Failed to restart chrony-wait.service: Unit chrony-wait.service not found.
```

