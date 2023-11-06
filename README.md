# 一键搭建VPS教程，最新的VLESS Vision和VLESS Reality防止VPS端口封禁


为了应对 TLS in TLS 和指纹识别等阻断或封禁的风险，Xray-core 团队推出了 VLESS Vision 和 VLESS Reality 两种新颖的技术方案。它们能够有效地隐藏和保护流量的特征，提高安全性和稳定性。

### Youtube视频教程：https://youtu.be/ha4XB13gAeU

 ## 一、准备工作

  ### 1、一台境外VPS主流系统，例如：Debian/Ubuntu/CentOS
Vultr是按时计费，不用了可以随时删除服务器就停止收费了，最低6$/月。

Vultr VPS 购买地址：https://www.vultr.com/?ref=9554306  [点此进入](https://www.vultr.com/?ref=9554306)  

### 2、下载并安装FinalShell SSH工具

Windows版下载地址：http://www.hostbuf.com/downloads/finalshell_install.exe  [点此下载](http://www.hostbuf.com/downloads/finalshell_install.exe)

macOS版下载地址：http://www.hostbuf.com/downloads/finalshell_install.pkg  [点此下载](http://www.hostbuf.com/downloads/finalshell_install.pkg)

## 二、搭建步骤

### 搭建脚本代码

    wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh


### 可参考的域名

这里输入的域名最低标准为：国外网站，支持 TLSv1.3 、H2 、没有被阻断，千万不要写被阻断的网站，注意红框的端口，这里必须添加。。

    # Apple
    gateway.icloud.com
    itunes.apple.com
    swdist.apple.com
    swcdn.apple.com
    updates.cdn-apple.com
    mensura.cdn-apple.com
    osxapps.itunes.apple.com
    aod.itunes.apple.com

    # mozilla
    download-installer.cdn.mozilla.net
    addons.mozilla.org

    # aws
    s0.awsstatic.com
    d1.awsstatic.com
    images-na.ssl-images-amazon.com
    m.media-amazon.com
    player.live-video.net

    # 其他
    one-piece.com
    lol.secure.dyn.riotcdn.net
    www.lovelive-anime.jp
    www.nokia.com
    auth.riotgames.com
    xsso.riotgames.com
    csgo.com


## 三、各平台客户端

v2rayNG【需要最新版本】

Windows（v2rayN）：https://github.com/2dust/v2rayN/releases/tag/6.23

Android（v2rayNG）：https://github.com/2dust/v2rayNG/releases/tag/1.8.5

IOS（shadowrocket）：https://apps.apple.com/app/shadowrocket/id932747118

## 四、放行端口
放行指令是一样的，只要将端口443为任意端口就可以了。

### 放行 443 端口

    iptables -I INPUT -p tcp --dport 443 -j ACCEPT

### 放行 54321 端口

    iptables -I INPUT -p tcp --dport 54321 -j ACCEPT


## 五、检测端口是否被封
端口被封的原因是多方面的，目前并没有哪一种节点可以保证不被封，本期讲的这种方式也不例外，所以如果你的节点突然无法使用了，可以用以下方式进行排查。

打开 [ping.pe](https://ping.pe/)

输入 IP 检测 ping 可用

输入 IP:Port 检查端口是否可用

主要是看最后几个是否为绿色




  
