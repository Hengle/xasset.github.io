<!-- docs/increament.md -->
## 增量模式

增量模式可以在编辑器把真机的 AssetBundle 加载以及版本更新环境还原。

和其他模式不同，增量模式需要在打包后手动执行以下菜单，把母包的资源复制到 StreamingAssets 下：

- **Assets/Versions/Copy To StreamingAssets**

这样，在启动编辑器的播放器后，在 StreamingAssets 中的资源会直接从其中加载，不在的，如果下载目录下没有，则会直接去服务器下载再加载，有的话，直接从下载目录加载。