为什么npx可以运行非全局安装的工具：

因为npx会自动本地的node_module里面的bin目录找到相应的文件。

如我使用npx webpack 会自动找到bin目录里面的webpack.cmd（windows环境下）

这个文件里面是window的一些脚本