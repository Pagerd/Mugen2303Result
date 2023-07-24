# oe_test_whereis

测试套问题， grep 测试的字串和实际不符

``whereis --help | grep "Usage: whereis"`` 失败，正确的输出如下：

```
# whereis --help

Usage:
 whereis [options] [-BMS <dir>... -f] <name>

Locate the binary, source, and manual-page files for a command.

Options:
 -b         search only for binaries
 -B <dirs>  define binaries lookup path
 -m         search only for manuals and infos
 -M <dirs>  define man and info lookup path
 -s         search only for sources
 -S <dirs>  define sources lookup path
 -f         terminate <dirs> argument list
 -u         search for unusual entries
 -l         output effective lookup paths

 -h, --help     display this help
 -V, --version  display version

For more details see whereis(1).
```


