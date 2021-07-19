<!-- docs/unpack-binary.md -->
##　解压二进制包

在创建 Build 的时候每个 Build 都提供了 PackBinary 的选项，如下图：

![example-build](res/example-build.png)

PackBinary 表示将打包后的散文件合并到一个二进制文件中。

如果一个模块的所有资源都没有包含在安装包，那么第一次更新时，可以通过下载这个模块的二进制来减少 IO。

以下是相关代码的一个示例：

```c#
var savePath = Versions.GetDownloadDataPath(Path.GetFileName(url));
PreloadManager.Instance.ShowProgress(Download.DownloadAsync(url, savePath,
    download =>
    {
        if (download.status == DownloadStatus.Success)
        {
            if (url.EndsWith(".bin"))
            {
                var unpackAsync = Versions.UnpackAsync(savePath);
                unpackAsync.updated += (message, progress) =>
                {
                    PreloadManager.Instance.SetMessage($"解压中...{message}", progress);
                };
                unpackAsync.completed += operation =>
                {
                    PreloadManager.Instance.SetMessage("解压完成", 1);
                    PreloadManager.Instance.SetVisible(false);
                };
            }
        }
        else
        {
            MessageBox.Show("提示", "下载失败，请检测网络链接后重试", isOk =>
            {
                if (isOk) StartDownload();
            });
        }
    }));
}
```