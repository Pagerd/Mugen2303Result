# oe_test_ccmake

x86 和 riscv 错误完全一致

```
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -B ../buildccmake -S ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "\r"}"
+ test -d ../buildccmake/CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 66'
+ message='oe_test_ccmake.sh line 66'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 66'
Tue Jun  6 15:13:12 2023 - ERROR - oe_test_ccmake.sh line 66
+ return 0
+ test -f ../buildccmake/CMakeCache.txt -a -f ../buildccmake/cmake_install.cmake -a -f ../buildccmake/Makefile
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 68'
+ message='oe_test_ccmake.sh line 68'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 68'
Tue Jun  6 15:13:14 2023 - ERROR - oe_test_ccmake.sh line 68
+ return 0
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -C ../../common/mysettings.cmake ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "\r"}"
+ test -d CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 94'
+ message='oe_test_ccmake.sh line 94'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 94'
Tue Jun  6 15:13:17 2023 - ERROR - oe_test_ccmake.sh line 94
+ return 0
+ test -f cmake_install.cmake -a -f CMakeCache.txt -a -f Makefile
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 96'
+ message='oe_test_ccmake.sh line 96'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 96'
Tue Jun  6 15:13:18 2023 - ERROR - oe_test_ccmake.sh line 96
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -DCMAKE_BUILD_TYPE:STRING=RELEASE ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "CMAKE_INSTALL_PREFIX:" {send "c"}"
+ test -d CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 118'
+ message='oe_test_ccmake.sh line 118'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 118'
Tue Jun  6 15:13:22 2023 - ERROR - oe_test_ccmake.sh line 118
+ return 0
+ test -f cmake_install.cmake -a -f CMakeCache.txt -a -f Makefile
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 120'
+ message='oe_test_ccmake.sh line 120'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 120'
Tue Jun  6 15:13:24 2023 - ERROR - oe_test_ccmake.sh line 120
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -UCMAKE_BUILD_TYPE ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "c"}"
+ test -d CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 142'
+ message='oe_test_ccmake.sh line 142'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 142'
Tue Jun  6 15:13:27 2023 - ERROR - oe_test_ccmake.sh line 142
+ return 0
+ test -f cmake_install.cmake -a -f CMakeCache.txt -a -f Makefile
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 144'
+ message='oe_test_ccmake.sh line 144'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 144'
Tue Jun  6 15:13:29 2023 - ERROR - oe_test_ccmake.sh line 144
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -G Unix Makefiles ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "c"}"
+ test -d CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 166'
+ message='oe_test_ccmake.sh line 166'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 166'
Tue Jun  6 15:13:32 2023 - ERROR - oe_test_ccmake.sh line 166
+ return 0
+ test -f cmake_install.cmake -a -f CMakeCache.txt -a -f Makefile
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 168'
+ message='oe_test_ccmake.sh line 168'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 168'
Tue Jun  6 15:13:34 2023 - ERROR - oe_test_ccmake.sh line 168
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake -G Ninja ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "c"}"
+ test -d CMakeFiles
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 191'
+ message='oe_test_ccmake.sh line 191'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 191'
Tue Jun  6 15:13:37 2023 - ERROR - oe_test_ccmake.sh line 191
+ return 0
+ test -f cmake_install.cmake -a -f CMakeCache.txt -a -f build.ninja
+ CHECK_RESULT 1
+ actual_result=1
+ expect_result=0
+ mode=0
+ error_log=
+ '[' -z 1 ']'
+ '[' 0 -eq 0 ']'
+ test 1x '!=' 0x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_ccmake.sh line 193'
+ message='oe_test_ccmake.sh line 193'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake.sh line 193'
Tue Jun  6 15:13:38 2023 - ERROR - oe_test_ccmake.sh line 193
+ return 0
```

