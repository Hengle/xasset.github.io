<!-- docs/changes -->
## 更新记录

### 7.0.5

**新特性**

- 自动热重载，已经加载的 AB 更新后，再次加载时自动卸载旧的，然后再加载新的版本
- Versions.GetDownloadSizeAsync 支持使用 不带 hash 的 bundle 名字，资源路径依旧有效
- 编辑器菜单层级优化，增加查看文档、提交问题等编辑器工具
- 命令行打包工具支持输入版本号

**其他**

- RawAsset 去掉 bytes 属性，建议使用 savePath 自行按需加载数据

### 7.0.4
**新特性**

- 母包资源加密支持（仅限团队版本，含 PlayAssetDelivery 部分）
- 独立 Unity 的源码工程，可以制作 dll（仅限团队版本，参考 Source 文件夹）

**其他**

- 原 AAB 包文件夹和名字空间改成 PAD
- AssetDatabase.FindAssets 调用优化，使用完整名字空间避免同名类型资源出现冲突。

### 7.0.3

**问题修复**

- 叠加场景在父场景回收后再卸载出现报错：改成父场景卸载后，只回收叠加场景的 Bundle，不执行具体卸载逻辑。

**其他**

- 调整 Versions 的名字空间为 VEngine，方便 Versions 类的 API 使用。 

### 7.0.2

**问题修复**

- ClearHistory 没有删除文件的问题。

### 7.0.1

**新功能**

- 分包打包支持黑名单机制，默认关闭，具体参考 PlayerConfig.blacklistMode 配置选项。
- 支持批量删除当前版本中选中资源的 Bundle 文件，UGUI 的图集和 Prefab 有时候修改图集后，Prefab 不会 Rebuild 可以删除 Prefab 后重新打包。

### 7.0

**主要内容**

- 全新的分布式构建系统（文档参考：https://xasset.github.io/ ）
- Android App Bundle 适配支持（母包可以超过 150MB）
- XLua 打包加载适配
- 更精炼的程序结构（编辑器+运行时核心代码不到5000行）
- 适配了 7.0 的示例

**注意事项**

- 7.0 开始将以 unitypackage 的形式提供源代码和示例，以及扩展模块。
- 7.0 提供了全新的授权模式，之前 6.1 的老用户继续沿用之前的授权模式，具体参考：https://xasset.github.io/#/team-plan 。
