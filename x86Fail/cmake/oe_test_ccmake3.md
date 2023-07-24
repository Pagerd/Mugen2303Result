# oe_test_ccmake3

x86 和 riscv 错误完全一致

```
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -B ../buildccmake3 -S ../../common/
Error opening terminal: unknown.
expect: spawn id exp3 not open
    while executing
"expect "*" {send "\r"}"
+ test -d ../buildccmake3/CMakeFiles
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 65'
+ message='oe_test_ccmake3.sh line 65'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 65'
Tue Jun  6 15:18:55 2023 - ERROR - oe_test_ccmake3.sh line 65
+ return 0
+ test -f ../buildccmake3/CMakeCache.txt -a -f ../buildccmake3/cmake_install.cmake -a -f ../buildccmake3/Makefile
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 67'
+ message='oe_test_ccmake3.sh line 67'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 67'
Tue Jun  6 15:18:57 2023 - ERROR - oe_test_ccmake3.sh line 67
+ return 0
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -C ../../common/mysettings.cmake ../../common/
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 92'
+ message='oe_test_ccmake3.sh line 92'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 92'
Tue Jun  6 15:19:01 2023 - ERROR - oe_test_ccmake3.sh line 92
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 94'
+ message='oe_test_ccmake3.sh line 94'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 94'
Tue Jun  6 15:19:02 2023 - ERROR - oe_test_ccmake3.sh line 94
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -DCMAKE_BUILD_TYPE:STRING=RELEASE ../../common/
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 116'
+ message='oe_test_ccmake3.sh line 116'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 116'
Tue Jun  6 15:19:05 2023 - ERROR - oe_test_ccmake3.sh line 116
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 118'
+ message='oe_test_ccmake3.sh line 118'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 118'
Tue Jun  6 15:19:07 2023 - ERROR - oe_test_ccmake3.sh line 118
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -UCMAKE_BUILD_TYPE ../../common/
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 140'
+ message='oe_test_ccmake3.sh line 140'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 140'
Tue Jun  6 15:19:10 2023 - ERROR - oe_test_ccmake3.sh line 140
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 142'
+ message='oe_test_ccmake3.sh line 142'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 142'
Tue Jun  6 15:19:12 2023 - ERROR - oe_test_ccmake3.sh line 142
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -G Unix Makefiles ../../common/
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 164'
+ message='oe_test_ccmake3.sh line 164'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 164'
Tue Jun  6 15:19:15 2023 - ERROR - oe_test_ccmake3.sh line 164
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 166'
+ message='oe_test_ccmake3.sh line 166'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 166'
Tue Jun  6 15:19:16 2023 - ERROR - oe_test_ccmake3.sh line 166
+ return 0
+ rm -rf './*'
+ '[' 23.03 '!=' 22.03 ']'
+ expect
spawn ccmake3 -G Ninja ../../common/
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 188'
+ message='oe_test_ccmake3.sh line 188'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 188'
Tue Jun  6 15:19:19 2023 - ERROR - oe_test_ccmake3.sh line 188
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
+ LOG_ERROR 'oe_test_ccmake3.sh line 190'
+ message='oe_test_ccmake3.sh line 190'
+ python3 /root/mugen-riscv/libs/locallibs/mugen_log.py --level error --message 'oe_test_ccmake3.sh line 190'
Tue Jun  6 15:19:20 2023 - ERROR - oe_test_ccmake3.sh line 190
+ return 0
```

