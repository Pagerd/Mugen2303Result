### oe_test_storage_nfs_restrict_hostname:连接超时/没有预装软件

riscv在进行ssh连接时超时

```
+ bash /root/mugen/libs/locallibs/sshcmd.sh -c 'yum install nfs-utils -y;mkdir /home/nfs;touch /home/nfs/testnfs;chmod -R 777 /home/nfs;
    mv /etc/exports /etc/exports.bak;echo '\''/home/nfs *(ro,sync,all_squash)'\'' >/etc/exports;' -i 10.198.114.3 -u root -p 'openEuler12#$' -t 300 -o 22
Fri Apr 28 08:17:55 2023 - WARN  - the remote user uses the default configuration.
Fri Apr 28 08:17:56 2023 - WARN  - the remote password uses the default configuration.
Fri Apr 28 08:17:57 2023 - WARN  - the connect port using the default configuration
spawn ssh -o ConnectTimeout=300 -p 22 root@10.198.114.3 yum install nfs-utils -y;mkdir /home/nfs;touch /home/nfs/testnfs;chmod -R 777 /home/nfs;
    mv /etc/exports /etc/exports.bak;echo '/home/nfs *(ro,sync,all_squash)' >/etc/exports;
ssh: connect to host 10.198.114.3 port 22: Connection timed out
```

而x86则没有iptables，因此测试失败

```
+ iptables -F
oe_test_storage_nfs_mount_readonly.sh: line 25: iptables: command not found
```

