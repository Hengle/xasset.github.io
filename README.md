<p align="center">
  <a href="https://game4d.cn/">
    <img src="https://game4d.cn/images/logo.png" alt="xasset logo" width="200" height="200">
  </a>
</p>

<h3 align="center">xasset</h3>

<p align="center">
  更快，更轻松的解决 Unity 项目的打包慢、包体大、资源更新、内存管理和运行卡顿之类的疑难杂症。
  <br>
  <a href="https://xasset.github.io"><strong>浏览文档 »</strong></a>
  <br>
  <br>
  <a href="https://github.com/xasset/xasset/issues/new?template=bug_report.md">报告问题</a>
  ·
  <a href="https://github.com/xasset/xasset/issues/new?template=feature_request.md">提交需求</a> 
</p>
## xasset <small>7.0</small>

xasset 7.0 是全面可靠的 Unity 资源系统。从开源版本到商业化，xasset 已经持续迭代了近 5 年，通过持续不断的自我迭代和突破 xasset 项目达成了：

- 1.4k+ 星标的开源项目（1.0-至今）
- 150+ 个人付费订阅（5.1-6.1）
- 35+ 团队付费订阅（持续增长 6.1-至今）
- 1k+ 用户的行业内容交流群（持续增长）
- 15+ 次创作赞助扶持（持续投入）

非常感谢新老用户的支持和鼓励！到 100+ 团队订阅的时候，我们将和大家分享：

——普通技术，如何在没有 buff 的情况下，不通过项目背书、不通过商业炒作，和各种注册资金过亿、千万+、百万+ 的公司、团队或个人建立服务关系。

希望我们探索出来的路，可以为更多的人提供指引。

## 发行版本

目前，xasset 7.0 主要发布了以下几个版本：

1. **体验版本**
   - MIT授权：https://github.com/xasset/xasset
2. **团队订阅版本**
   - 普通授权：https://github.com/mmdnb/xasset-pro
   - 旗舰授权：https://github.com/mmdnb/xasset-ue
3. **个人订阅版本**
   - 长期用户：https://github.com/mmdnb/xasset-lts
   - 特殊用户：https://github.com/mmdnb/xasset-se
   - 普通用户：https://github.com/mmdnb/xasset-base

阅读[版本比较](compares.md)可以比较细致的了解体验源版本和团队订阅版本的差异，而订阅版本中，个人相对团队主要是剥离了以下功能：

- 高性能资源加密功能
- Google Play 分包适配
- XLua 适配

通常，一般项目用开源版本足够了，而对于体量比较大，或是对更新机能、安全性以及性能等方面有更高标准的项目来说，订阅团队版本，不仅可以帮老板省钱，也能帮自己节省时间。

## 新的改进

对比上一个开源版本（4.x），7.0 最大的变化是：

- 编辑器和运行时高度剥离，代码结构更精炼和模块化。
- 使用只读的物理文件数据进行版本管理，版本检测稳定性和效率得到前所未有的提高。 
- 打包后的文件的文件名自带文件内容的版本信息，天生可以避免CDN缓存问题以及一些其他的冲突。
- 全新的多线程文件下载组件，真机环境比之前 UnityWebRequest 版本更稳定。
- 自动分帧机制为程序运行的流畅度提供保障。
- 加载资源默认支持自动更新。

> 注：开源版本中，同步加载如果触发自动更新可能会报错，订阅版本会更强大一些。

对比上一个订阅版本（6.1），7.0 最大的变化是：

- 全新的分布式构建系统，可以更快更灵活的大包。
- 编辑器+运行时的代码量减少了近 3000 行，程序结构更精炼，且更好扩展。
- Android App Bundle + Play Asset Delivery 适配（仅限团队版本）。
- 基于 XLua 的 Lua 文件打包加载适配（仅限团队版本）。
- 高性能安装包资源加密（仅限团队版本）。
- 自动热重载技术。

## 最近更新

### 7.0.5(2021年8月13日)

**新特性**

- 自动热重载，已经加载的 AB 更新后，再次加载时自动卸载旧的，然后再加载新的版本
- Versions.GetDownloadSizeAsync 支持使用 不带 hash 的 bundle 名字，资源路径依旧有效
- 编辑器菜单层级优化，增加查看文档、提交问题等编辑器工具
- 命令行打包工具支持输入版本号

**其他**

- RawAsset 去掉 bytes 属性，建议使用 savePath 自行按需加载数据

### 7.0.4(2021年8月12日)

**新特性**

- 母包资源加密支持（仅限团队版本，含 PlayAssetDelivery 部分）
- 独立 Unity 的源码工程，可以制作 dll（仅限团队版本，参考 Source 文件夹）

**其他**

- 原 AAB 包文件夹和名字空间改成 PAD
- AssetDatabase.FindAssets 调用优化，使用完整名字空间避免同名类型资源出现冲突。

> 阅读[修改记录](changes.md)可以了解更多历史内容。

## 功能特性

- 分布式增量打包，分包打包，安装包资源加密。
- Android App Bundle & Play Asset Delivery 适配，Google Play 的首包大小不受 150 MB 的限制。  
- 使用只读的物理文件数据进行版本管理，版本检测稳定性和效率得到前所未有的提高。 
- 支持预先对局部内容进行下载更新，或是在加载资源的时候进行自动更新。
- 支持多线程并发下载，可以限速、断点续传，文件内容指纹校验以及异常恢复。   
- 统一使用相对路径加载资源或场景，自动管理依赖，支持异步转同步，兼容 Android、iOS、WebGL、PC、OSX 等平台。
- 支持仿真模式、预加载模式、增量模式，编辑器下可以轻松模拟真机的资源加载和更新环境。

此外，xasset 7.0 会集中处理系统的更新操作，支持最大单帧处理时间片设置，超时自动分帧，并提供异步实例化、异步渐进式回收、异步仿真加载等支持，流畅运行有保障。 

## 了解更多

- 有关 xasset 的疑问或建议，请加作者微信号 vmakemore 反馈。

## 技术支持

团队订阅的用户可以在专属对接群留言，其他用户可以先查阅文档或是[点击链接加入群聊【GAME+】](https://jq.qq.com/?_wv=1027&k=7DpHQNhb)给群主留言。