自建订阅转换
可以有效防止订阅泄露以及规则下载不全等问题

订阅转换后端项目地址：[subconverter](https://github.com/tindy2013/subconverter)

Windos系统中的使用方法
转换时确保可以正常访问Github；如无法访问，在https://raw.githubusercontent.com前添加https://ghproxy.com/
点击下载[subconverter_win64.7z](https://github.com/tindy2013/subconverter/releases/download/v0.8.1/subconverter_win64.7z)
解压至本地，双击subconverter.exe，等待命令窗弹出
按需求修改并复制转换规则至浏览器，回车打开，确认规则是否完整
更新链接时必须运行subconverter.exe
转换规则

完整配置(可直接导入使用)

http://localhost:25500/sub?target=clash&insert=true&new_name=true&scv=true&url=机场订阅地址&config=自定义ini配置文件

Node List配置（只包含节点信息）

http://localhost:25500/sub?target=clash&insert=true&new_name=true&scv=true&url=机场订阅地址&list=true

多国家 流媒体 自动最低延迟

https://github.com/Repcz/Tool/raw/X/Clash/Premium/Online_Full_Auto.ini

多国家 流媒体 手动选择

https://github.com/Repcz/Tool/raw/X/Clash/Premium/Online_Full_NoAuto.ini


Docker中的使用方法
确保服务器可以正常访问Github
在终端中输入
docker run -d --restart=always -p 25500:25500 tindy2013/subconverter:latest
等待1分钟，运行以下命令，如看见subconverter vx.x.x backend即正常运行
curl http://localhost:25500/version
按需求修改并复制转换规则至浏览器，回车打开，确认规则是否完整
如果访问异常，请重启docker并等待1分钟后重试
转换规则

完整配置(可直接导入使用)
http://服务器地址:25500/sub?target=clash&insert=true&new_name=true&scv=true&url=机场订阅地址&config=自己专属的ini配置文件
Node List配置（只包含节点信息）
http://服务器地址:25500/sub?target=clash&insert=true&new_name=true&scv=true&url=机场订阅地址&list=true
自用ini配置文件

多国家 流媒体 自动最低延迟
https://github.com/Repcz/Tool/raw/X/Clash/Premium/Online_Full_Auto.ini
多国家 流媒体 手动选择
https://github.com/Repcz/Tool/raw/X/Clash/Premium/Online_Full_NoAuto.ini
参数说明
调用参数	必要性	示例	解释
target	必要	target=clash	指想要生成的配置类型，详见 [支持类型](https://github.com/Repcz/Tool/tree/0bd8de4ce9f765fd04a94fe7d150bf4bcc440944/subconverter#%E6%94%AF%E6%8C%81%E7%B1%BB%E5%9E%8B) 中的参数
insert	可选	true / false	用于设置是否将配置文件中的 insert_url 插入，默认为 true
new_name	可选	true / false	如果设置为 true，则将启用 Clash 的新组名称 (proxies, proxy-groups, rules)
scv	可选	true / false	用于关闭 TLS 节点的证书检查，默认为 false
url	必要	url=机场订阅地址	指机场所提供的订阅链接或代理节点的分享链接
config	可选	config=自己专属的ini配置文件	指 外部配置 的地址 (包含分组和规则部分)，需要经过 [URLEncode](https://www.urlencoder.org/) 处理，详见 [外部配置](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#%E5%A4%96%E9%83%A8%E9%85%8D%E7%BD%AE) ，当此参数不存在时使用 主程序目录中的配置文件
list	可选	true / false	用于输出 Surge Node List 或者 Clash Proxy Provider 或者 Quantumult (X) 的节点订阅 或者 解码后的 SIP002
更多参数调用参阅[调用说明 (进阶)](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#%E8%B0%83%E7%94%A8%E8%AF%B4%E6%98%8E-%E8%BF%9B%E9%98%B6)

本文参考:
[subconverter/README-cn.md](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#subconverter)
[自建clash订阅转换subconverter后端并配置规则](https://s1oz.github.io/post/zi-jian-clash-ding-yue-zhuan-huan-hou-duan-bing-pei-zhi-gui-ze/)
[解决订阅转换节点被盗用和无法转换大量节点，本地订阅转换教程](https://www.youtube.com/watch?v=UxvjT_nHLo4)
