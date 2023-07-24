### oe_test_FSIO_dir_access_sbin: ls -l /usr/sbin错误

riscv与x86报错相同

下为对应log

```
++ ls -l /usr/sbin
++ awk '{print $1}'
++ uniq
++ grep -v total
++ cut -c 1-10
++ sort
+ actual_access='lrwxrwxrwx
-r--r--r--
-rwsr-xr-x
-rwx------
-rwxr-xr-x
-rwx--s--x
-r-xr-xr-x'
+ read rows
+ [[ lrwxrwxrwx
-r--r--r--
-rwsr-xr-x
-rwx------
-rwxr-xr-x
-rwx--s--x
-r-xr-xr-x =~ lrwxrwxrwx ]]
+ continue
+ read rows
+ [[ lrwxrwxrwx
-r--r--r--
-rwsr-xr-x
-rwx------
-rwxr-xr-x
-rwx--s--x
-r-xr-xr-x =~ -rwsr-xr-x ]]
+ continue
+ read rows
+ [[ lrwxrwxrwx
-r--r--r--
-rwsr-xr-x
-rwx------
-rwxr-xr-x
-rwx--s--x
-r-xr-xr-x =~ -rwx------ ]]
+ continue
+ read rows
+ [[ lrwxrwxrwx
-r--r--r--
-rwsr-xr-x
-rwx------
-rwxr-xr-x
-rwx--s--x
-r-xr-xr-x =~ -rwxr-x--- ]]
```

