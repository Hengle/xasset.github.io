<!-- docs/getstarted.md -->
## 快速开始

获得 xasset 订阅的授权后，可以通过对应授权的地址下载 xasset 的源码到本地：

- 团队授权：https://github.com/mmdnb/xasset-pro
- 团购授权：https://github.com/mmdnb/xasset-se
- 长期授权：https://github.com/mmdnb/xasset-lts
- 基础授权：https://github.com/mmdnb/xasset-base

将以上仓库的内容下载到本地后，可以执行以下步骤快速体验示例项目：

1. 使用 Unity 新建一个叫 xasset-example 的项目；

2. 将 **xasset-6.1.x-example.unitypackage** 导入到这个项目；

3. 使用 XASSET/Groups 菜单打开打包编辑器，如下图：

   <img src="\res\getstarted-groups-editor.png"/>

4. 使用打包编辑器的 Build/AllBundles 执行打包命令，并将 ScriptPlayMode 修改为 Incremental 模式，如下图：

   <img src="\res\getstarted-build-bundles.png"/>

5. 将打包后的资源部署到 hfs 中，如下图：

   <img src="\res\getstarted-hfs.png"/>

6. 在设置中，把 DefualtSettings 中的 BuildPlayerGroupsIndex 改成 2，并 使用 XASSET/Build/Copy To StreamingAssets，将打包后的资源按需复制到包体资源目录，如下图：

   <img src="\res\getstarted-buildplayergroupsindex.png"/>

7. 打开 Startup 场景点击播放，如下图：

   <img src="\res\getstarted-startup-play.png"/>

8. 播放后，首先会显示 POWERED BY XASSET 的闪屏，然后进入欢迎场景，如下图：

   <img src="\res\getstarted-welcome.png"/>

!> 注：示例是基于 Unity 2019.4 开发的。
