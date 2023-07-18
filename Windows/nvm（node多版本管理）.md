## nvm  node多版本安装管理

nvm下载地址：https://github.com/coreybutler/nvm-windows/releases

1. 进入下载地址，下载 nvm-setup.exe；
2. 安装前卸载本地已安装的node；
3. 双击安装包进行安装；
4. 打开CMD，输入命令 `nvm`命令查看是否安装成功；
5. 到安装路径下找到文件setting.txt。在最后添加以下代码

```
node_mirror: https://npm.taobao.org/mirrors/node/

npm_mirror: https://npm.taobao.org/mirrors/npm/
```



nvm相关命令

```
nvm -h   // 查看所有命令；

nvm list  // 查看当前安装的nodeJS的版本；这里有星号标注的说明是当前使用的nodeJS版本

nvm install v11.15.0  // 指定安装v11.15.0 的nodeJS；

nvm use v11.15.0  // 指定使用某版本的nodeJS；

nvm uninstall 11.15.0  // 卸载指定版本的nodeJS；
```

