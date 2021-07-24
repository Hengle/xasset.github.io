## 欢迎使用 xasset-7.0

xasset-7.0 是精炼、强大的 Unity 资源系统。

xasset-7.0 主要为 Unity 项目的包体大、打包慢、版本更新、边玩边下、运行卡顿等疑难杂症提供全面有效的解决方案。

## 功能特点

xasset-7.0 提供了精炼、强大的程序代码，并且一切设计都为解决生产环境的痛点、难点服务，这主要包括：

**打包**

- 分布式、单工程多模块按需增量打包，配置、UI、场景等资源可以按需分批次提交给构建管线，加快打包进程。
- 分包打包、可以针对不同平台（渠道）预定义不同大小的首包内容，例如，完整资源、部分资源、不带资源。
- 支持自动分析依赖、自动优化冗余、自动解决冲突，10W 贴图不用分布式可以 10 分钟完成打包。
- 团队版支持 Android App Bundle，Google Play 的首包大小不受 150 MB 的限制。 

**更新**

- 可以按需对局部内容进行更新，也可以进行全量增量更新，加载资源支持自动更新。
- 文件名自带版本信息，天生没有同名缓存问题，同时更新的文件不会和正在使用的文件产生冲突。
- 使用只读的清单文件管理版本信息，没有频繁的文件版本状态写入操作，稳定性++，效率++。

**下载**

- 可限速、可以控制并发数量，边玩边下无压力，轻松查询速度和大小。
- 支持断点续传，没下载完成的文件，中途退出后，下次可以继续下载。
- 自修复异常，不论是网络异常还是，内容校验异常，默认会进行 3 次自动重试的自修复操作，减少业务中断。
- 支持文件指纹校验，对于设置了 crc 的下载数据，下载完成后，会对文件内容进行 crc 比对，比对不通过会删除进度，并启动自修复机制。

**加载**

- 统一使用相对路径加载资源，一次编码可以到处运行，支持短链接，可以使用自定义的路径替换默认加载路径。
- 支持异步转同步，异步加载还未完成时，执行同步加载可以让异步加载立即完成。
- 支持 ScenesInBuild 和 AssetBundle 中的场景的异步加载，均支持 Single 和 Additive 模式，支持 AssetBundle 中的资源的同步和异步加载。
- 使用引用计数进行内存管理，不重复加载、进多少、出多少。
- 支持仿真模式、预加载模式、增量模式，编辑器可以和真机无缝切换。
- 支持 Android、iOS、WebGL、PC、OSX 等平台。

此外，xasset-7.0 会集中处理系统的更新操作，支持最大单帧处理时间片设置，超时自动分帧，并提供异步实例化、异步渐进式回收、异步仿真加载等支持，流畅运行有保障。 

## 主要优势

xasset 订阅服务，不通过上线项目背书，不搞商业炒作，累计创收 10W+，用户覆盖了中国 TOP20 营收公司的 40%+ 团队或个人，自然离不开：

- 强大的功能，精炼的代码，编辑器 + 运行时的源代码不到 5000 行（Unity 官方 3w+ 行代码），解决问题单刀直入，不绕弯子（充钱就能变强）。 
- 丰富的示例，循环依赖加载、叠加场景加载、下载解压二进制、边玩边下、异步转同步、下载限速、更新版本信息、获取下载大小、更新下载进度速度，基本都是开箱即用。
- 贴心的售后，购买 xasset 的订阅服务，将至少获得 1 年的更新支持，并且还可以按需购买其他附加服务，例如：Project Review、性能基线划分、工作流程优化等。

更少的成本，更大的收获，这就是选择和使用 xasset 最大的优势。

## 历史记录

从开源版本到商业化，xasset 已经持续迭代了近 5 年，通过持续不断的自我迭代和突破 xasset 项目达成了：

- 1.4k+ 星标的开源项目（1.0-4.x）
- 160+ 个人和团队付费订阅（5.1-6.1）
- 近 30+ 团队付费订阅（持续增长 6.1）
- 1k+ 用户的行业内容交流群（持续增长）
- 15+ 次创作赞助扶持（持续投入）

非常感谢新老用户的支持和鼓励，祝大家一起越做越好！

## 了解更多

- 有关 xasset 的疑问或建议，请加作者微信号 vmakemore 反馈。

## 技术支持

团队订阅的用户可以在专属对接群留言，个人用户可以先查阅文档或是[点击链接加入群聊【GAME+】](https://jq.qq.com/?_wv=1027&k=7DpHQNhb)给群主留言。
