# oe_test_openssl_DSA_algorithm

测试套问题， x86 和 riscv 失败原因一致

测试脚本 Line 23-26 如下所示

```
    openssl dsaparam -noout -out dsakey.pem -genkey 2048
    CHECK_RESULT $?
    grep 'BEGIN DSA PRIVATE KEY' dsakey.pem
    CHECK_RESULT $?
```

dsakey.pem 示例如下

```
-----BEGIN PRIVATE KEY-----
MIICXgIBADCCAjYGByqGSM44BAEwggIpAoIBAQD2RZMvV80FPto1Y9gVAdWyRRJO
G0cbEPzsE5z1JBWvk0BE66VgWY2cP87ctdsVTvgY1luJMIRRpjM8lUzPK/lrT2jO
2tmYg7/xE3v21sTYKsM5mYvuxgNeyZcKJ2UiHhG3bQlKG7B1CLOLXZd42Htl3P9m
vI/gsuIF8DhlthjUsR3mp7oTQlFT866IbZTLBAI0I/Fz4Ln59Ti6/80iBC0/R8GY
aCFtVORRo2Wcej6LNobVSrLtKj7o6VE7m4KNp7Wncp6Wnkab+LRnHPdKl2BPPXw8
pnlk1C2DyYH7HRP+dTr8Oi8EN6qwUCYPSojNfb/yW4/lbSubez0NpYJ31MVLAh0A
2iOCpy9xxfzI6A2p1yY2CZODIQA2afp303QYBwKCAQEA6ESty/TW9PK8ZWEz7Y4w
/l6xDr+JAv7xljRQWjRrTGMWxvC6j2oggy3N2utIKKj5x5WOVLyz4ZOLqqemZS7n
4KFwuSnjHpv1FUazOXk827hSz+btWyVO9G2vGf13EI7yUOdpDPpLL/GYSwyJDIZr
dWD9zAtyio/7uOQP+P1qbLrTsF7jZZc0WuzJ+eQ6odWHtbttZiEVuObJlRkorRTz
3Qol4XWwwk2ZSTnmll0fojtPujd3sNHvzgfslH0VhBRmvouUBlfKpLFaf1+VeVWC
Y0nsO99nHh4RJpTzsM9Qr/E3fXXC0AiqUSDCpddz/k8K+oEKYTGQKcN4oF/ghBkZ
TAQfAh0AvB/NQUZW2in4di5etelrFM9lyOc+fi5Xl0b5JA==
-----END PRIVATE KEY-----
```

可见 grep 参数和实际不符，导致测试失败。

