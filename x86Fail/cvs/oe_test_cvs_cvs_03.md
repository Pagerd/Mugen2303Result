### oe_test_cvs_cvs_03:测试用例没有权限执行操作,初始化失败

 riscv与x86报错均相同

在配置环境时报出以下错误

```
++ su cvsroot
cvs init: cannot open /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT/config: Permission denied
cvs [init aborted]: cannot make directory /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir: Permission denied
cvs [import aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
++ cvs -d /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir checkout myProject
cvs [checkout aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: No such file or directory
++ chown -R cvsroot.cvs myProject
chown: cannot access 'myProject': No such file or directory
++ chmod -R 775 myProject
chmod: cannot access 'myProject': No such file or directory
++ cd myProject
./init/cvs_complex.sh: line 37: cd: myProject: No such file or directory
++ chown -R cvsroot.cvs tmp.txt
chown: cannot access 'tmp.txt': No such file or directory
++ su cvsroot
cvs [commit aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
bash: line 2: tmp.txt: Permission denied
bash: line 3: 1.txt: Permission denied
mkdir: cannot create directory ‘dir’: Permission denied
touch: cannot touch 'dir/2.txt': No such file or directory
bash: line 4: dir/2.txt: No such file or directory
cvs [add aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
cvs [add aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
cvs [commit aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
```

在随后的测试中对应报错log为

```
+ su cvsroot -c 'cvs tag rel-1-0 | grep '\''T tmp.txt'\'''
cvs [tag aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
+ CHECK_RESULT 1 0 0 'test cvs tag failed'
```

