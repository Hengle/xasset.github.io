<!-- docs/load-scene.md -->
## 场景加载

在 xasset 7.0 中，不论是 ScenesInBuild 中的场景，还是打包 AssetBundle 的场景，都是使用下面这个接口进行加载:

- Scene.LoadAsync

以下是加载场景的示例代码：

```c#
// 加载一个 Single 场景
Scene.LoadAsync(pathToScene);

// 加载一个 叠加场景
Scene.LoadAdditiveAsync(pathToScene);
```

需要注意的是，场景加载主要包括 Additive 和 Single 两种模式，每次加载一个新的 Single 模式的场景后，之前加载的所有场景将会自动释放。

所以，Single 场景不需要主动调用 Release，而 Additive 场景如果不需要使用的时候，可以主动调用 Release 释放场景。