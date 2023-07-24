### oe_test_skopeo

执行`skopeo inspect --tls-verify=false docker://docker.io/nginx`时会报错提示目标镜像镜像没有riscv架构：

```
FATA[0003] Error parsing manifest for image: choosing image instance: no image found in manifest list for architecture riscv64, variant "", OS linux
```



或者直接程序崩溃，原因不明，报错在日志里。