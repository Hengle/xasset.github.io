<!-- docs/update-versions.md -->

## 更新版本信息

更新版本信息主要用来同步最新的清单文件。

xasset-7.0 版本信息主要由以下两部分组成:

- Manifest: 每个 Build 对应的清单文件（包含了每个 Build 中所有资源的版本信息）
- ManifestVersion：每个清单文件对应的版本文件（内容小，只包含清单文件的版本信息）

版本信息的更新流程是：

1. 下载清单的版本文件
2. 对比版本文件对应的清单是否已经下载
    - 如果下载了，就不再下载清单，直接转到 3
    - 如果没下载，就先下载清单，下载完成后再转到 3
3. 按需进行清单文件的装载
    - 对于安装包内部的清单，会先检查其对于的下载目录的清单是否存在，如果存在并且下载目录的清单版本 > 内部版本，直接加载下载目录的版本，否则加载内部版本
    - 对于服务器的清单，仅当版本发生变化时会读取数据到内存，当用户确认更新后才会覆盖内部版本的清单文件

以下是更新版本信息的示例代码：

```c#
var updateAsync = Versions.UpdateAsync("manifest1_hash", "manifest2_hash", "manifestx_hash");
yield return updateAsync;
if (updateAsync.status == OperationStatus.Failed)
{
    yield return MessageBox.Show("提示", "更新版本信息失败，请检测网络链接后重试。", ok =>
    {
        if (ok)
            StartUpdate();
        else
            OnComplete();
    }, "重试", "跳过");
    yield break;
}
```

需要注意的是，在没有调用以下接口前，服务器的清单只是下载到本地，而不会覆盖已有的版本文件：

```c#
updateAsync.Override();
```

如果需要高版本兼容低版本的支持，可以把 Override 的操作，可以放到获取更新大小之后，不需要的化可以在更新完成后直接调用，然后再执行以下代码：

```c#
updateAsync.Dispose();
```