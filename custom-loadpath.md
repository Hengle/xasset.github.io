<!-- docs/custom-loadpath.md -->
## 自定义加载地址

默认，xasset-7.0 使用 Assets 开头的相对路径加载资源，但是，如果有特殊需要，可以通过在初始化之前，实现这个代理：

- Versions.customLoadPath

重定义加载地址，以下是相关代码的实现参考：
