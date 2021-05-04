---
sidebar_position: 8
---

# 翻墙进行服务授权

在UWP应用中，OAuth之类的网络授权通常是使用[WebAuthenticationBroker](https://docs.microsoft.com/en-us/windows/uwp/security/web-authentication-broker)进行的。

它看起来像一个独立的浏览器窗口:

![](/img/rss-stalker/auth.png)

它是以IE作为浏览器核心的，所以你可能会发现，即便你开了VPN或代理，在通过该授权窗口访问外网时依然会出现`无法连接服务`的提示，这个时候，请按以下步骤操作：

:::tip
前提是，你要真的能通过代理访问被屏蔽的网站（比如可以通过浏览器打开，而且不是用的专属于浏览器的插件）
:::

### 1. 下载相关工具

出现无法访问服务的原因在于UWP特有的本地网络环回限制，它使得UWP应用无法走本地代理通道，我们要做的就是解除这个限制。

我尝试做了个小工具，顺带测一下Project Reunion，你可以直接下载（包比较大）：

[Loopback Manager](https://github.com/Richasy/LoopbackManager/releases/tag/v0.0.1)

如果你难以访问Github，或者想使用精简版（包很小），也可以从百度网盘下载：

[百度网盘](https://pan.baidu.com/s/10r4raod7IdZUzxKlybI3mw)，提取码 2s3c

### 2. 解除限制

:::tip
顺带把RSS Tracker也给选上，这样可以保证代理的顺利运行
:::

下载之后打开该exe文件（需要管理员权限），在搜索栏中输入`auth`，你能看到下列的一些应用服务：

![](/img/rss-stalker/loopback.png)

*当然，你看到的可能没这么多，也许只有一个，总之是这种格式的应用服务。*

将其全部勾选，并点击`Save`按钮，接下来请重启《RSS追踪》，然后你就可以正常进行授权了。