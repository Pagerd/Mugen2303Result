### oe_test_qpdf_qpdf_01：测试套编写错误

riscv与x86报错均相同

对应报错log如下

```
+ qpdf --help
+ grep 'argument help'
+ CHECK_RESULT 1 0 0 'qpdf --help running failed'
+ actual_result=1
+ expect_result=0
```

实际使用qpdf --help时出现以下结果

```
[root@openeuler-riscv64 ~]# qpdf --help
Run "qpdf --help=topic" for help on a topic.
Run "qpdf --help=--option" for help on an option.
Run "qpdf --help=all" to see all available help.

Topics:
  add-attachment: attach (embed) files
  advanced-control: tweak qpdf's behavior
  attachments: work with embedded files
  completion: shell completion
  copy-attachments: copy attachments from another file
  encryption: create encrypted files
  exit-status: meanings of qpdf's exit codes
  general: general options
  help: information about qpdf
  inspection: inspect PDF files
  json: JSON output for PDF information
  modification: change parts of the PDF
  overlay-underlay: overlay/underlay pages from other files
  page-ranges: page range syntax
  page-selection: select pages from one or more files
  pdf-dates: PDF date format
  testing: options for testing or debugging
  transformation: make structural PDF changes
  usage: basic invocation

For detailed help, visit the qpdf manual: https://qpdf.readthedocs.io

```

因此为测试套编写错误