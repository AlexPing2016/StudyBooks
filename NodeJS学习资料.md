# 第一章 Node.js概述
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
npm install 包模块名 --save-dev    局部安装包模块，并把包依赖信息写入配置文件devdependencies中，例如webpack,gulp开发阶段使用的包
npm install 包模块名 --save        局部安装包模块，并把包依赖信息写入配置文件dependencies中，例如Express、jQuery发布后还要使用的包
npm unstall 包模块名               删除安装包模块
npm  list                         显示安装的npm包
npm  show  包模块名                显示具体模块的信息
```
* 全局安装配置文件（npmrc）
  * 文件路径 C:\Program Files\nodejs\node_modules\npm 
  * 设置新的全局安装路径
  * 修改环境变量Path中的新路径
```
     prefix = 新的安装路径
     cache  =  新的安装路径（缓存文件）
```
## 镜像安装设置
* 通过命令使用淘宝镜像
```
  npm install 包模块名 --save --registry=https://registry.npm.taobao.org
```
* 通过配置使用淘宝镜像
```
  在npmrc文件中添加以下配置项
  registry=https://registry.npm.taobao.org
```
## yarn简介
* FaceBook的包管理工具
* 常用命令
  *  初始化新项目
  ```
    yarn init
  ```
  *  添加一个依赖包
    ```
      yarn add [包模块]
     yarn add [包模块]@[version]
     yarn add [包模块]@[tag]
  ```
  *  更新一个依赖包
   ```
       yarn upgrade [包模块]
  yarn upgrade [包模块]@[version]
  yarn upgrade [包模块]@[tag]
  ```
  *  删除一个依赖包
  ```
    yarn remove [包模块]
  ```
  *  安装所有依赖包
    ```
   yarn 或 yarn install
  ```

   
   
