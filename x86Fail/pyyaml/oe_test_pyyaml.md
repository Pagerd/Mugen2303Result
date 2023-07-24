### oe_test_pyyaml：测试用例没有更新测试方法

riscv与x86均报相同错误，具体log如下：

```
Traceback (most recent call last):
  File "/root/mugen/testcases/cli-test/pyyaml/test2.py", line 21, in <module>
    get_yaml_data(yaml_path)
  File "/root/mugen/testcases/cli-test/pyyaml/test2.py", line 15, in get_yaml_data
    data = yaml.load(file_data)
TypeError: load() missing 1 required positional argument: 'Loader'

+ CHECK_RESULT 1 0 0 'Conversion to dictionary failed'
```

错误原因为Yaml 5.1版本后就舍弃了 yaml.load(file) 这个用法。Yaml 5.1版本之后为使得load函数的安全性得以提高，就修改了需要指定Loader，通过默认加载器（FullLoader）禁止执行任意函数。而测试用例并没有更新