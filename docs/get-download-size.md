<!-- docs/get-download-size.md -->
## 获取下载大小

获取下载大小主要通过如下接口实现：

- Versions.GetDownloadSizeAsync

以下是调用该接口的代码示例：

```c#
var getDownloadSize = Versions.GetDownloadSizeAsync(updateAsync, group.assets);
yield return getDownloadSize;
if (getDownloadSize.totalSize > 0 || updateAsync.changed)
{
    var messageBox = MessageBox.Show("提示",
        $"发现更新({Utility.FormatBytes(getDownloadSize.totalSize)})：服务器版本号 {updateAsync.version}，本地版本号 {Versions.ManifestsVersion}，是否更新？",
        null, "更新", "跳过");
    yield return messageBox;
    if (messageBox.ok)
    {
        updateAsync.Override();
        StartDownload(getDownloadSize);
        yield break;
    }
}
```

updateAsync 是之前更新版本信息时返回的对象，这表示直接使用服务器的版本信息进行检查，如果只想针对本地的版本信息进行检查可以使用这个版本：

```c#
var getDownloadSize = Versions.GetDownloadSizeAsync(group.assets);
yield return getDownloadSize;
if (getDownloadSize.totalSize > 0)
{
    var messageBox = MessageBox.Show("提示",
        $"发现更新({Utility.FormatBytes(getDownloadSize.totalSize)})：服务器版本号 {updateAsync.version}，本地版本号 {Versions.ManifestsVersion}，是否更新？",
        null, "更新", "跳过");
    yield return messageBox;
    if (messageBox.ok)
    {
        StartDownload(getDownloadSize);
        yield break;
    }
}
```

通常，只有第一次进行版本更新才传入更新版本信息时返回的对象，后续的内容都可以使用本地的版本信息进行检查。需要注意的是 group.assets 是一组资源列表，为什么不使用 group 的名字而是使用列表呢？这主要是游戏的内容会随着时间轴的变化而变化，预先制作的东西具有一定时效性，传入一个动态列表更灵活。