##### oe_test_container-exception-logger:

没有对应的riscv的docker包,下为对应的log文件

```
+ wget -q https://repo.openeuler.org/openEuler-23.03/docker_img/riscv64/openEuler-docker.riscv64.tar.xz
+ docker load
oe_test_container-exception-logger.sh: line 29: openEuler-docker.riscv64.tar.xz: No such file or directory
++ docker images --format '{{.Repository}}:{{.Tag}}'
```

### 