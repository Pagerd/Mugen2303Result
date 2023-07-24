### oe_test_cvs_cvs_04:测试用例初始化失败

 riscv与x86报错均相同

在配置环境时报出以下错误

```
cvs [checkout aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: No such file or directory
++ chown -R cvsroot.cvs myProject
chown: cannot access 'myProject': No such file or directory
++ chmod -R 775 myProject
chmod: cannot access 'myProject': No such file or directory
++ cd myProject
./init/cvs_complex.sh: line 37: cd: myProject: No such file or directory
++ chown -R cvsroot.cvs tmp.txt
++ su cvsroot
cvs [commit aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
bash: line 3: 1.txt: Permission denied
mkdir: cannot create directory ‘dir’: Permission denied
touch: cannot touch 'dir/2.txt': No such file or directory
bash: line 4: dir/2.txt: No such file or directory
cvs [add aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
cvs [add aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
cvs [commit aborted]: /root/mugen/testcases/cli-test/cvs/cvs_test/cvs_init_dir/CVSROOT: Permission denied
```

在随后的测试中没有多余的报错



