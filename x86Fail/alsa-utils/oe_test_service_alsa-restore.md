### oe_test_service_alsa-restore

测试之前没有安装pciutils，所以没有lspci工具，直接没过下面这个判断：

```
    if ! lspci | grep -i audio; then
        LOG_INFO "The environment does not support testing"
        exit 1
```



由于启动时没有添加音频设备，所以安装pciutils之后依然会报错。

在高于7.0版本的qemu中使用`-audiodev pa,id=snd0 -device usb-audio,audiodev=snd0`参数添加音频设备，会出现以下报错`qemu-system-riscv64: -audiodev pa,id=snd0: Parameter 'driver' does not accept value 'pa'`。

在低于7.0版本的qemu中使用参数`-device intel-hda -device hda-duplex`可以成功添加音频设备，此时在x86中测试成功，在risc-v中测试失败：用命令lspci可以找到音频设别，但是用命令aplay -l显示没有声卡。

更新：

ubuntu中安装pulseaudio`sudo apt install pulseaudio`，然后用命令`systemctl --user start pulseaudio`启动pulseaudio服务，再将启动脚本改为如下：

```
cmd="qemu-system-riscv64 \
  -nographic -machine virt \
  -smp "$vcpu" -m "$memory"G \
  -bios "$fw" \
  -drive file="$drive",format=qcow2,id=hd0 \
  -object rng-random,filename=/dev/urandom,id=rng0 \
  -device intel-hda -device hda-duplex \
  -device virtio-vga \
  -device virtio-rng-device,rng=rng0 \
  -device virtio-blk-device,drive=hd0 \
  -device virtio-net-device,netdev=usernet \
  -netdev user,id=usernet,hostfwd=tcp::"$ssh_port"-:22 \
  -device qemu-xhci -usb -device usb-kbd -device usb-tablet \
  -audiodev pa,id=snd0 -device usb-audio,audiodev=snd0"
```



即可通过测试。