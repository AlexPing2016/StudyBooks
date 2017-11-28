# Node.js学习
## Node.js的安装
* [官方网址](https://nodejs.org/en/)
  * LTS:稳定版本
  * CURRENT:最新版本
* 使用步骤
  * 根据自己的系统选择下载版本
  * 执行安装文件
  * 验证是否成功 ```node -v```
## npm包管理
* [官方网址](https://nodejs.org/en/)
* 常用命令
```
npm init                          生成配置文件package.json（加-y采用默认参数）
npm install -g 包模块名            全局安装包模块（install可以简写成i）
npm install 包模块名 --save-dev    局部安装包模块，并把包依赖信息写入配置文件中，工具包加dev，普通函数库--save即可
npm  list                          显示安装的npm包
npm  show  包模块名                 显示具体模块的信息
```
* 全局安装配置文件（npmrc）
  * 文件路径 C:\Program Files\nodejs\node_modules\npm 
  * 设置新的全局安装路径
```
     prefix = 新的安装路径
     cache  =  新的安装路径（缓存文件）
```
