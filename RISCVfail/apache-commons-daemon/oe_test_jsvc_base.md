### oe_test_jsvc_base

没有做riscv的适配，只有arm和x86的包：

```
function pre_test() {
  LOG_INFO "Start environmental preparation."
  DNF_INSTALL "apache-commons-daemon tar"
  mkdir tmp && cd tmp
  if test "$(uname -i)"X == "x86_64"X; then
    echo 'get x86 architecture apache-commons-daemon pkg'
    cp ../common/x86/apache-commons-daemon.tar.gz ./
    tar -xvf apache-commons-daemon.tar.gz
  else
    echo 'get arm architecture apache-commons-daemon pkg'
    cp ../common/arm/apache-commons-daemon.zip ./
    unzip apache-commons-daemon.zip
  fi
  cd apache-commons-daemon
  current_path=$(
    cd "$(dirname $0)" || exit 1
    pwd
  )
  tar -xvf *.tar.gz
  LOG_INFO "End of environmental preparation!"
}
```



common目录中也只有arm和x86的包。