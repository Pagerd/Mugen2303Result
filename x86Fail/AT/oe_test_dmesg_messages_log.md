### oe_test_dmesg_messages_log

oerv在dmesg中有不少报错信息：

```
[    0.801329] syscon-poweroff: probe of poweroff failed with error -16
[    0.804027] riscv-pmu-sbi: Perf sampling/filtering is not supported as sscof extension is not available
[ 9280.523477] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[10242.592051] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[11225.529926] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[12193.559976] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[13237.422999] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[14314.496504] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[15421.609070] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[16324.471698] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[17345.464831] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[18296.481135] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[19361.581037] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[20333.402876] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[21315.396326] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[22908.392342] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[23904.481955] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[26773.576304] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[27717.333955] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[28747.405090] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[29802.411159] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[30762.401223] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[32709.421065] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[32709.529001] systemd[1]: dnf-makecache.service: Main process exited, code=exited, status=1/FAILURE
[32709.534805] systemd[1]: dnf-makecache.service: Failed with result 'exit-code'.
[32709.548195] systemd[1]: Failed to start dnf makecache.
[33789.389317] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[34695.360003] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[35674.364424] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[36697.409252] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[38589.531631] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[39571.353585] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[41609.313755] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
[46376.437773] systemd[1]: systemd-journald.service: Failed with result 'watchdog'.
```





oerv没有/var/log/messages这个文件：

```
grep: /var/log/messages: No such file or directory
```



x86下/var/log/messages文件中有不少报错信息：

```
May 26 02:06:09 localhost kernel: [    1.752638] jitterentropy: Initialization failed with host not compliant with requirements: 2
May 26 02:06:09 localhost rngd[253]: [rdrand]: Initialization Failed
May 26 02:06:14 localhost rngd[253]: [jitter]: Initialization Failed
May 26 02:06:14 localhost rngd[253]: [pkcs11]: Initialization Failed
May 26 02:06:24 localhost systemd-tmpfiles[1021]: /usr/lib/tmpfiles.d/systemd.conf:19: Failed to resolve user 'systemd-network': No such process
May 26 02:06:24 localhost systemd-tmpfiles[1021]: /usr/lib/tmpfiles.d/systemd.conf:20: Failed to resolve user 'systemd-network': No such process
May 26 02:06:24 localhost systemd-tmpfiles[1021]: /usr/lib/tmpfiles.d/systemd.conf:21: Failed to resolve user 'systemd-network': No such process
May 26 02:06:24 localhost systemd-tmpfiles[1021]: /usr/lib/tmpfiles.d/systemd.conf:22: Failed to resolve user 'systemd-network': No such process
May 26 02:06:45 localhost kernel: [   52.117456] Error: Driver 'pcspkr' is already registered, aborting...
May 26 02:06:53 localhost kdumpctl[1594]: Starting kdump: [FAILED]
May 26 02:06:53 localhost systemd[1]: kdump.service: Main process exited, code=exited, status=1/FAILURE
May 26 02:06:53 localhost systemd[1]: kdump.service: Failed with result 'exit-code'.
May 26 02:06:53 localhost systemd[1]: Failed to start Crash recovery kernel arming.
May 26 02:06:54 localhost kernel: [   60.914046] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.923272] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.932507] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.944536] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.946294] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.953691] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.959211] powernow_k8: Power state transitions not supported
May 26 02:06:54 localhost kernel: [   60.959245] powernow_k8: Power state transitions not supported
May 26 02:11:15 localhost [RPM][5001]: install perl-Error-1:0.17029-3.oe2303.noarch: success
May 26 02:11:18 localhost [RPM][5001]: install perl-Error-1:0.17029-3.oe2303.noarch: success
May 26 03:10:49 localhost dnf[5582]: Failed determining last makecache time.
May 26 03:50:39 localhost kernel: [    1.777871] jitterentropy: Initialization failed with host not compliant with requirements: 2
May 26 03:50:39 localhost rngd[254]: [rdrand]: Initialization Failed
May 26 03:50:44 localhost rngd[254]: [jitter]: Initialization Failed
May 26 03:50:44 localhost rngd[254]: [pkcs11]: Initialization Failed
May 26 03:50:54 localhost systemd-tmpfiles[1031]: /usr/lib/tmpfiles.d/systemd.conf:19: Failed to resolve user 'systemd-network': No such process
May 26 03:50:54 localhost systemd-tmpfiles[1031]: /usr/lib/tmpfiles.d/systemd.conf:20: Failed to resolve user 'systemd-network': No such process
May 26 03:50:54 localhost systemd-tmpfiles[1031]: /usr/lib/tmpfiles.d/systemd.conf:21: Failed to resolve user 'systemd-network': No such process
May 26 03:50:54 localhost systemd-tmpfiles[1031]: /usr/lib/tmpfiles.d/systemd.conf:22: Failed to resolve user 'systemd-network': No such process
May 26 03:51:02 localhost dracut-pre-pivot[1212]: ln: failed to create symbolic link '/sysroot/boot/initramfs-6.1.19-7.0.0.17.oe2303.x86_64.img': File exists
```

