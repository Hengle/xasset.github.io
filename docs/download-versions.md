<!-- docs/download-versions.md -->
## 批量下载文件

批量下载文件是一种一次下载多个文件的操作。在获取下载大小后，如果内容有更新，可以通过以下代码，启动下载：

```c#
var downloadAsync = Versions.DownloadAsync(getDownloadSize.result.ToArray());
yield return downloadAsync;
if (downloadAsync.status == OperationStatus.Failed)
{
    var messageBox2 = MessageBox.Show("提示！", "下载失败！请检查网络状态后重试。", null);
    yield return messageBox2;
    if (messageBox2.ok)
        StartDownload(getDownloadSize);
    else
        OnComplete();
    yield break;
}
```

注：为了更快的响应异常，批量下载文件在内部是 one by one 的下载。