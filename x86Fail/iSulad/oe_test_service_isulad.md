# oe_test_service_isulad

x86 和 riscv 失败原因完全一致

```
+ journalctl --since '2023-05-31 07:49:33' -u isulad.service
+ grep -i 'fail\|error'
+ grep -v -i 'DEBUG\|INFO\|WARNING'
May 31 07:49:35 openeuler-riscv64 isulad[535]:          isulad 20230530234935.230 ERROR    /home/abuild/rpmbuild/BUILD/iSulad-v2.1.1/src/utils/cutils/utils_file.c:util_list_all_subdir:953 - Failed to open directory: /var/lib/isulad/engines error:No such file or directory
May 31 07:49:35 openeuler-riscv64 isulad[535]:          isulad 20230530234935.234 ERROR    /home/abuild/rpmbuild/BUILD/iSulad-v2.1.1/src/daemon/modules/container/restore/restore.c:containers_restore:549 - Failed to list engines
May 31 07:49:51 openeuler-riscv64 isulad[561]:          isulad 20230530234951.703 ERROR    /home/abuild/rpmbuild/BUILD/iSulad-v2.1.1/src/utils/cutils/utils_file.c:util_list_all_subdir:953 - Failed to open directory: /var/lib/isulad/engines error:No such file or directory
May 31 07:49:51 openeuler-riscv64 isulad[561]:          isulad 20230530234951.705 ERROR    /home/abuild/rpmbuild/BUILD/iSulad-v2.1.1/src/daemon/modules/container/restore/restore.c:containers_restore:549 - Failed to list engines
+ CHECK_RESULT 0 0 1 'There is an error message for the log of isulad.service'
``

