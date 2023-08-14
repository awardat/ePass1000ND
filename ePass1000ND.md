# ePass1000ND与安装软件



ePass1000ND为免驱动版本，无需专门安装驱动，插入系统后会被识别为USB输入设备。但是此时是不能使用的，还需要安装中间件提供标准接口和状态显示。[下载SDK](https://mega.nz/file/3N01iaCT)（[密钥](Mu1ss00yPPMBSoiFtnXTqtBSwXtxNFqWJ0BiI20_z38)）使用[7-Zip-zstd](https://github.com/mcmilk/7-Zip-zstd)解压，[解压密码](0FA.,5=UY}L.O~cV)。

在将设备插入USB接口后操作系统会自动作为HID设备安装驱动，在设备管理器中可见位于人机接口设备\USB输入设备，使用AIDA64可见HID Token M32.

![USB设备](img/hid_in_usb.png)

此时是不能对设备进行操作的，还需要安装中间件实现与设备的通信，运行eps1knd_stdSimpChinese.exe安装中间件，一路下一步完成就可以了。

![安装中间件](img/midware_inst.png)

同时在系统通知栏会多出一个ePassNG证书管理工具的图标，双击弹出主窗口

![ePassNG证书管理工具](img/ePass_CertMgr.png)

证书管理工具中显示了当前令牌和其中安装的证书，可以显示证书信息，如果是新的或者初始化过的令牌则证书栏为空。

**首次初始化**

如果插入令牌后，证书管理工具提示”KEY已插入“，但是在选择令牌的地方却是空白的，表示令牌尚未进行过初始化，需要运行PKIInit_M32.exe对令牌进行首次初始化。

![初始化令牌](img/new_ukey_init.png)

根据提示按回车初始化令牌，在初始化时证书管理工具会快速的弹出令牌初始化过程的提示，直到提示初始化完成后按ESC退出初始化程序，初始化完成会创建默认SOPIN和USERPIN，重试次数为15次。

| 账号    | 口令   |
| ------- | ------ |
| SOPIN   | rockey |
| USERPIN | 1234   |

**注：** 此工具仅可对首次使用的新令牌进行初始化（我将其称为首次初始化），已经进行过首次初始化的令牌需要使用下述管理工具进行初始化进行复位。

进行过初始化后即可使用ePassNG PKI 管理工具（管理员）查看和管理令牌

![ePassNG PKI 管理工具](img/epass_mgr_adm.png)

在此界面上可以看到令牌信息和管理功能，还有一个用户版管理软件，主要少了最下行三个按钮的功能。

点击初始化进行令牌初始化界面，输入SOPIN，新的USERPIN进行初始化，如果不知道SOPIN则无法进行初始化。

> USERPIN支持大小写字母、数字和符号

![初始化令牌](img/ukey_init.png)

点击登录输入USERPIN后即可查看和管理令牌中保存的数据。

![数据管理](img/data_mgr.png)

可以在此界面导入PFX、P12、P7B、X509格式证书，查看已有的证书信息，导出公钥和证书，删除证书。