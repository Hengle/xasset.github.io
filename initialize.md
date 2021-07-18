<!-- docs/initialize.md -->
## 初始化

初始化主要完成平台路径的设置以及母包的清单文件的加载，以下是初始化的示例代码：

```c#
var operation = Versions.InitializeAsync();
yield return operation;
Logger.I("Initialize: {0}", operation.status);
Versions.DownloadURL = downloadURL;
Logger.I("API Version: {0}", Versions.APIVersion);
Logger.I("Manifests Version: {0}", Versions.ManifestsVersion);
Logger.I("PlayerDataPath: {0}", Versions.PlayerDataPath);
Logger.I("DownloadDataPath: {0}", Versions.DownloadDataPath);
Logger.I("DownloadURL: {0}", Versions.DownloadURL);
```

注：在使用其他运行时API前，请先确保系统以及正常初始化了。