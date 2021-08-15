<!-- docs/load-asset.md -->
## 常规资源加载

常规资源指的是除了场景外所有打包 AssetBundle 的资源，对此，xasset 7.0 提供了以下接口进行加载：

- Asset.Load(Async): 同步(异步)加载

以下是加载常规资源的代码示例：

```c#
// 加载文本
var asset = Asset.Load(pathToAsset, typeof(TextAsset));
var ta = asset.asset as TextAsset;
var text = ta.text;
// 如果需要加载文本中的二进制可以这样:
var bytes = ta.bytes;

// 加载 Sprite
var asset = Asset.Load(pathToAsset, typeof(Sprite));
var sprite = asset.asset as Sprite;

// 加载 Texture
var asset = Asset.Load(pathToAsset, typeof(Texture));
var texture = asset.asset as Texture;

// 加载 prefab
var asset = Asset.Load(pathToAsset, typeof(Object));
var prefab = asset.asset as Object;
// 如果要在场景中创建 prefab 的 GameObject 可以这样：
var gameObject = GameObject.Instantiate(prefab);

// 加载 音频
var asset = Asset.Load(pathToAsset, typeof(AudioClip));
var clip = asset.asset as AudioClip;

// 加载 ScriptableObject
var asset = Asset.Load(pathToAsset, typeof(ScriptableObject));
var so = asset.asset as ScriptableObject;
```

限于篇幅，这里暂且列举这么多，可以参考 AssetDatabase.LoadAssetAtPath 的使用方法来使用 Asset.Load(Async)。
