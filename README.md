# XiaomiCTSPass
### 强制小米设备通过谷歌CTS测试.

#### 描述信息
- 此项目为Magisk模块，可在Magisk Manager App或第三方Recovery（本质还是依赖Magisk环境）中刷入。

#### 支持机型
- 后续会支持更多机型

| 机型 | 内部代号 | 最低安卓版本 | 最高安卓版本 | 官方维护状态 |
| :----: | :----: | :----: | :----: | :----: |
| 小米 MIX3 | perseus | Android 9 | Android 10 | × |
| 小米 MIX2 | chiron | Android 7.1 | Android 9 | × |
| 小米 MIX2S | polaris | Android 9 | Android 10 | × |
| 小米11 | venus | Android 11 | Android 11 | √ |
| 小米11 Ultra | star | Android 11 | Android 11 | √ |
| 小米10 | umi | Android 10 | Android 11 | √ |
| 小米10至尊纪念版 | cas | Android 10 | Android 11 | √ |
| 小米10 Pro | cmi | Android 10 | Android 11 | √ |
| 小米10S | thyme |  Android 11 | Android 11 | √ |
| 小米10青春版 | vangogh | Android 10 | Android 11 | √ |
| 小米9 | cepheus | Android 9 | Android 10 | √ |
| 小米9 SE | grus | Android 9 | Android 11 | √ |
| 小米CC9 | pyxis | Android 9 | Android 10 | √ |
| 小米8 | dipper | Android 9 | Android 10 | × |
| 小米8屏幕指纹版 | equuleus | Android 9 | Android 10 | × |
| 小米8 SE | sirius | Android 8.1 | Android 10 | × |
| 小米6 | sagit | Android 7.1 | Android 9 | × |
| 小米5 | gmini | Android 6 | Android 8 | × |
| 小米平板4 | clover | Android 8.1 | Android 8.1 | × |
| Redmi K40 | alioth | Android 11 | Android 11 | √ |
| Redmi K40 Pro | haydn | Android 11 | Android 11 | √ |
| Redmi K30 4G | phoenix | Android 10 | Android 11 | √ |
| Redmi K30 5G | picasso | Android 10 | Android 11 | √ |
| Redmi K30 Pro | lmi | Android 10 | Android 11 | √ |
| Redmi K30 至尊纪念版 | cezanne | Android 10 | Android 10 | √ |
| Redmi K30S 至尊纪念版 | apollo  | Android 10 | Android 10 | √ |
| Redmi K20 | davinci | Android 9 | Android 10 | √ |
| Redmi K20 Pro | raphael | Android 9 | Android 10 | √ |
| Redmi NOTE9 | cannon | Android 10 | Android 10 | √ |
| Redmi NOTE9 Pro | gauguin | Android 10 | Android 11 | √ |
| Redmi NOTE8 | ginkgo | Android 9 | Android 11 | √ |
| Redmi NOTE8 Pro | begonia | Android 9 | Android 10 | √ |
| Redmi NOTE7 | lavender | Android 9 | Android 10 | × |
| Redmi NOTE7 Pro | violet |  Android 9 | Android 10 | × |

#### 自定义扩展
- `./XiaomiCTSPass/props/`下的文件名格式为`机型代号_sdk及版本号.prop`，以安卓11（SDK版本号为30）的小米10机型为例，扩展文件名应为`umi_sdk30.prop`。
- 从小米设备的稳定版固件中提取`ro.build.fingerprint` `ro.build.description` `ro.build.version.security_patch`属性，具体参考`./XiaomiCTSPass/props/`下的文件内容。
- 可提取其他机型的属性强行适配某机型，但文件名格式必须严格按照某机型信息填写（此种可能有bug，自测）。

#### 如何使用
- 下载源码，然后直接make编译出模块（也可在Releases直接下载已经生成的模块）
- 面具安装添加编译出来的模块

#### 特别说明
- 系统跨版本升级时会自动比对fingerprint（指纹）属性，所以每次系统升级后会自动禁用XiaomiCTSPass模块；更新完开机后，重启一次，即可自动启用XiaomiCTSPass模块
- 刷完后须手动开启magisk hide
- 建议搭配[Universal SafetyNet Fix模块](https://github.com/kdrag0n/safetynet-fix)使用
- 禁用或启用XiaomiCTSPass模块时，需重新载入参数，首次开机时间变长属于正常情况

#### 特别感谢
- [XDA帖子](https://forum.xda-developers.com/t/module-magiskhide-props-config-safetynet-prop-edits-and-more-v5-4-0.3789228/)
- [SK](https://github.com/sekaiacg)对此模块亦有贡献
