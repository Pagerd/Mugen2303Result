### oe_test_pcp_pcp-import-ganglia2pcp:没有安装对应软件

riscv在使用service命令时出错，显示不存在此命令

```
 service gmond restart
oe_test_pcp_pcp-import-ganglia2pcp.sh: line 43: service: command not found
+ service httpd restart
oe_test_pcp_pcp-import-ganglia2pcp.sh: line 44: service: command not found
+ service gmetad restart
oe_test_pcp_pcp-import-ganglia2pcp.sh: line 45: service: command not found
+ P_SSH_CMD --node 2 --cmd '
        sed -i '\''/ name / s/unspecified/cluster01/'\'' /etc/ganglia/gmond.conf;
        service gmond restart;'
+ python3 /root/mugen/libs/locallibs/ssh_cmd.py --node 2 --cmd '
        sed -i '\''/ name / s/unspecified/cluster01/'\'' /etc/ganglia/gmond.conf;
        service gmond restart;'
bash: line 3: service: command not found
```

x86则是没有安装wget但是使用了wget命令

```
+ wget -nd http://jaist.dl.sourceforge.net/sourceforge/collectl/collectl-3.1.3.src.tar.gz
oe_test_pcp_pcp-import-collectl2pcp.sh: line 23: wget: command not found
+ tar zxvf collectl-3.1.3.src.tar.gz
tar (child): collectl-3.1.3.src.tar.gz: Cannot open: No such file or directory
tar (child): Error is not recoverable: exiting now
tar: Child returned status 2
tar: Error is not recoverable: exiting now
```

