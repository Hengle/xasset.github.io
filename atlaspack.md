<!-- docs/atlaspack.md -->
## 图集打包

图集打包，主要讲解的是 Unity 的 SpriteAtlas 相关资源的打包，这里可以直接参考：[SpriteAtlas与AssetBundle最佳食用方案](https://www.cnblogs.com/msxh/p/14194756.html)。

## 为什么使用 SpriteAtlas？

对比旧的设置 tag 的方式打图集，SpriteAtlas 是一种分布式的设计，可以更方便的预览单个图集的内容。

对比第三方的图集制作方案，SpriteAtlas 是一种后处理的图集构建方案，使用时无需关注资源在哪个图集。

## 核心规则

- 一个 AssetBundle 可以包含多个图集，但是同一个图集的内容必须要打包到统一个 AssetBundle。