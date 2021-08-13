<!-- docs/menuitems.md -->
## 编辑器工具

xasset-7.0 主要提供了如下编辑器工具：

**创建配置**

- Assets/Create/Versions/Settings 创建一个基本设置文件
- Assets/Create/Versions/Build 创建一个打包配置
- Assets/Create/Versions/Group 创建一个资源组，可以用来指定首包的资源，以及运行时获取更新大小时的资源。
- Assets/Create/Versions/Command Line Tools 创建命令行工具，创建后会生成 Build Bundles 和 Build Player 功能对应的 bat 和 sh 文件，可以放到 CI 环境中使用。

**版本管理**

- Assets/Versions/Build Bundles 打包所有资源
- Assets/Versions/Build Player 打包安装包
- Assets/Versions/Build AssetPacks(AAB) 团队订阅仅有
- Assets/Versions/Copy To StreamingAssets 根据配置复制首包的资源到 StreamingAssets，编辑器下在进行增量模式测试的时候可以用到
- Assets/Versions/Clear Build 清理所有打包数据，危险操作谨慎执行
- Assets/Versions/Clear History 清理不在当前版本的历史打包数据，可以按需执行
- Assets/Versions/Clear Download 清理编辑器的下载目录的数据
- Assets/Versions/Clear Temporay 清理临时目录的数据（主要包含清单和清单的版本文件）