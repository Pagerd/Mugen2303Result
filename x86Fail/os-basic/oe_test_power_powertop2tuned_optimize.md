# oe_test_power_powertop2tuned_optimize

x86 和 riscv 报错完全一致

```
+ powertop2tuned new_profile_name --force
Your Powertop version is incompatible (maybe too old) or the generated HTML output is malformed
Running PowerTOP, please wait...
+ CHECK_RESULT 101

+ tuned-adm profile new_profile_name
Cannot talk to TuneD daemon via DBus. Is TuneD daemon running?
Requested profile 'new_profile_name' doesn't exist.
+ CHECK_RESULT 1
+ actual_result=1
```

