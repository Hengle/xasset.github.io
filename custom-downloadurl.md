<!-- docs/custom-downloadurl.md -->
## 自定义下载地址

自定义下载地址是可以按需使用的功能，使用自定义下载地址可以避免某些资源使用独特的下载地址的时候污染默认下载地址的情况，当然也可以按需用作其他情况。

以下是使用自定义下载地址的代码示例：

```c#
Versions.CustomDownloadURL = url =>
{
    if (url.EndsWith("arts"))
    {
        return url + "arts_hash";
    }
    return null;
};
```

就像上面的代码一样，如果输入的 url 需要使用自定义下载地址就返回自定义的下载地址，不需要则返回 null。