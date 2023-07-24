### cppcheck

##### oe_test_cppcheck:

对应log如下

```
+ cppcheck -DA --force file.c
+ grep A=1
file.c:5:6: error: Array 'a[10]' accessed at index 10, which is out of bounds. [arrayIndexOutOfBounds]
    a[10] = 0;
     ^
Checking file.c: A=1...
+ CHECK_RESULT 0 1
+ actual_result=0
+ expect_result=1
+ mode=0
+ error_log=
+ exit_mode=0
+ '[' -z 0 ']'
+ '[' 0 -eq 0 ']'
+ test 0x '!=' 1x
+ test -n ''
+ (( exec_result++ ))
+ LOG_ERROR 'oe_test_cppcheck.sh line 95'
+ message='oe_test_cppcheck.sh line 95'
+ python3 /root/mugen/libs/locallibs/mugen_log.py --level error --message 'oe_test_cppcheck.sh line 95'
Tue May 30 17:01:24 2023 - ERROR - oe_test_cppcheck.sh line 95
```

测试用例内如下

```
if [ $VERSION_ID != "22.03" ]; then
        cppcheck -DA --force file.c | grep "A=1"
        CHECK_RESULT $? 1
    else
        cppcheck -DA --force file.c | grep "A=1"
        CHECK_RESULT $?
    fi
```

根据输出结果疑似为测试时23.03特性与22.03相符但是测试套没有更新