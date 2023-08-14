# ePass1000ND
前几天在做淘宝看广告任务的时候发现，飞天诚信ePass1000ND提供标准安全中间件CSP接口，提供标准安全中间件PKCS#11接口，支持多个密钥的存储，最高可存储6对密钥；硬件实现数字签名，支持X.509 v3标准证书格式，能与多种PKI应用无缝集成等等功能。并且这东西几十元一枚，应用需求没那么多的情况下比Yubikey实惠多了。

在网上搜了一下，使用这个作为个人应用的例子还是挺少见的，只找到一篇[uKey双向认证https](https://juejin.cn/post/6885609293891141645)可以作为参考的，配套工具只有某收费站点有下载，而且也不知道是不是完整，于是找了一个贵一点但是提供SDK的商家买了一枚。

**PS:** Yubikey相关使用记录看[这里](https://github.com/awardat/YubiKey-Guide_CHS)

## 选购

我选择的是飞天诚信 ePass1000ND 3.0版本，应该也是现在的最新版本。理论上说更早的版本也可以用，但是对于这种无法升级固件的设备来说还是尽量使用新版本为上。

理论上 ePass系列的其他产品也可以实现相同效果。

从飞天日本官网找到一个[产品对比表](https://ftsafe.co.jp/products/epass_n/epass_compare/)搬过来。

| 機能 | ePass1000ND                                                  | ePass2003      | ePass3003      | ePass3003Auto   |
| ---- | ------------------------------------------------------------ | -------------- | -------------- | --------------- |
| 存储空间（字节）                              | 32K             | 64K            | 64K             | 64K           |
| 存储类型                                                 | EEPROM          | 16位IC卡 | 32位IC卡 | 32位IC卡 |
| 身份验证方法                                               | PIN | PIN | PIN | PIN |
| 存储证书                                             | ○               | ○ | ○ | ○ |
| 私有API Web认证                                 | ○               | ×              | ×               | ×               |
| Windows  (32bit)                 | ○               | ○ | ○ | ○ |
| Windows  (64bit) | ○               | ○ | ○ | ○ |
| Linux                                                        | ×              | ○              | ○               | ○               |
| MacOS（10.6以上）                                            | ×               | ○ | ○COS V6.1以上     | ○  |
| PKCS#11、Microsoft CAPI、X.509 v3 CertificateStorage、SSL v3、IPSec/IKE | ○               | ○ | ○ | ○ |
| ISO 7816-3 、 4                                         | –               | ○              | ○               | ○               |
| PC/SC規格                                                    | ×               | ○              | ×               | ×               |
| 驱动                                                     | 不要            | 不要           | 不要            | 不要            |
| 中间件                                                 | ○               | ○ | ○ | ○ |

从对比表中可以看到ePass1000ND并不支持标准智能卡，所以也不支持某些需要标准智能卡实现的功能，比如无法用于保存BitLocker证书等。

根据日本官网提供的信息，[ePass2003](https://ftsafe.co.jp/products/epass_n/epass2003/)似乎更适合个人使用，功能完整，价格也比较适中.

## 令牌与安装

[ePass1000ND](ePass1000ND.md)

## 应用与软件

[获取GDCA免费邮件签名证书](get_DGCA_email_cert.md)

[使用令牌保存VeraCrypt密钥](VeraCrypt_with_token.md)



