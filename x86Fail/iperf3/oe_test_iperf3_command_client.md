# oe_test_iperf3_command_client

riscv 计算有误

```
+++ iperf3 -c 10.0.0.4 -w 20240
+++ grep sender
+++ awk '{print $5}'
+++ iperf3 -c 10.0.0.4 -w 102400
+++ grep sender
+++ awk '{print $5}'
++ expr 261 '>' 1.06
+ '[' 1 -eq 0 ']'
+ CHECK_RESULT 1 0 0 'iperf3 -w execution failed.'
```

