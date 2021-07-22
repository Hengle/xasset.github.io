<!-- docs/mrc.md -->
## 引用计数

引用计数主要用来防止对象重复加载，以及使用中的对象被提前卸载。

xasset-7.0 的引用计数规则比较简单：

- Load 的时候默认引用计数会自增 1
- Release 的时候引用计数会自减 1

此外，如果对象加载失败，底层默认会自动 Release 一次。

所以，在使用 xasset-7.0 进行资源管理的时候，一般只要不踩 Unity 的这些坑：

- Android 下，Camera 引用的 AssetBundle 中的 RendererTexture，需要先把 Camera.targetTexture 置空后，才能正常回收。 

只要确保 Load 的次数和 Release 的次数一致，资源就会得到正常回收。