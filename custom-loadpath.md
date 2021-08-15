<!-- docs/custom-loadpath.md -->
## 自定义加载地址

默认，xasset 7.0 使用 Assets 开头的相对路径加载资源，但是，如果有特殊需要，可以通过在初始化之前，实现这个代理：

- Versions.customLoadPath

重定义加载地址，以下是相关代码的实现参考：

```c#
// ...
Versions.customLoadPath = LoadByNameWithoutExtension;
var initialize = Versions.InitializeAsync();
yield return initialize;
```

LoadByNameWithoutExtension 方法的实现如下：

```c#
private string LoadByNameWithoutExtension(string assetPath)
{
    // loadKeys = { "Prefabs/" };
    if (loadKeys == null || loadKeys.Length == 0) return null; 
    if (!Array.Exists(loadKeys, assetPath.Contains)) return null; 
    var assetName = Path.GetFileNameWithoutExtension(assetPath);
    return assetName;
}
```

需要注意的是，自定义的加载路径需要自行规避同名冲突，如果不想使用自定义的加载路径就返回 null。