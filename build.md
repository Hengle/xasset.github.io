<!-- docs/build.md -->

## 打包的基本介绍

打包主要包含两个部分：

- 打包资源
- 打包播放器（安装包）

## 打包资源

xasset 使用一个叫 Build 的可序列化类对象来配置单次要打包的所有资源组，并实现具体打包细节。

打包资源的流程主要包括：

### 1. 创建 Build

创建 Build 主要通过执行这个菜单命令完成：

- **Assets/Create/Versions/Build**

以下是一个已经创建好的叫 Arts 的 Build 对象的在 Inspector 的截图：

![example-build](res\example-build.png)

Build 对象主要包含如下属性：

- Auto Group 是否开启自动分组，自动分组会把参与打包的资源的依赖收集起来，对于被多个资源引用但是没有指定分组的资源，默认会添加到一个自动分组中，这是处理常规资源冗余的最快方式。
- Pack Binary 是否将打包后的离散文件合并到一个二进制文件中，合并的二进制文件可以用来做整包更新，减少IO次数。
- Groups 参与打包的分组配置，分组的 Target 可以设置为文件或者文件夹，是文件夹时，还可以通过 Filter 指定只针对哪种资源。
- Options 打包 AB 的选项，常规资源使用 Chunk 格式，包含视频的分组需要使用 Uncompress 格式。

### 2. 添加 Group

一个 Build 可以包含多个 Group，可以直接修改 Build 对象的 Groups 的 Size 添加新的 Group。以下是 Group 的属性说明：

- Name 当 Bundle Mode 为 Pack Together 的时候会按这个名字把采集到的资源一起打包。
- Active 是否启用，启用后，在执行打包的时候才会采集这个分组的资源。
- Bundle Mode 默认提供了5 个不同粒度的打包模式，具体参考[Bundle Mode的配置说明](# Bundle Mode 的配置说明)。
- Target 要打包的目标对象，可以是单个文件，或者文件夹，是文件夹的时候可以通过 Filter 限定采集的资源类型。
- Filter 当 Target 是文件夹的时候有效，具体参考 https://docs.unity3d.com/ScriptReference/AssetDatabase.FindAssets.html。
- Handle Dependencies 是否处理依赖，通常 Prefab、Scene、Animation 之类的文件需要开启依赖处理，而 Shader、Textures、Text Asset 之类不需要开启依赖处理，按需开启可以优化打包速度。

### 3. 为 Group 选择 Bundle Mode

Bundle Mode 主要决定了资源的打包方式。除了 Pack By Raw 外，都是把资源打包成 Asset Bundle，以下是 Bundle Mode 的属性说明：

- Pack Together 把采集到的资源打包到一起。
- Pack By File 把采集的资源每个文件单独打包。
- Pack By Directory 把采集的资源按其所在的目录打包。
- Pack By Top Directory 把采集的资源按其相对 Target 的一级子目录打包。
- Pack By Raw 把采集的资源按原始格式打包。

### 4. 执行 Build

执行打包后，默认执行的操作依次是：采集资源->自动分组（可选）->生成清单->生成记录



## 打包播放器

## 术语

- **Asset Bundle**

  用来实现 Unity 的资源热更的数据结构

- **Raw Asset**

  原始格式的资源
