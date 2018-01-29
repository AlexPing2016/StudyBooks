# Webpack应用
## 一、Webpack概述
Webpack是一个模块加载器以及打包工具，能把各种资源，例如js、样式和图片等作为模块进行使用和处理。
   
* 支持CommonJS和AmdJS模块
* 支持其他模块的加载器，例如babel
* 通过配置打包多个文件
* 支持SCSS,SASS样式文件预处理，和图片资源等的打包
## 二、安装

1. 安装nodejs
2. 全局安装webpack
 
`npm install -g webpack`
  
3. 项目文件夹初始化
 
`npm init`
  
4. 项目文件夹中安装webpack
 
`npm install --save-dev  webpack`
    
## 三、基本应用

1. 打包文件的基本方法
 
  `webpack  源文件  目标文件`
   
2. 利用配置文件进行打包1
 
 * 项目根路径下添加webpack.config.js配置文件
 * 在上述配置文件中，添加配置项
   >
   >* module.exports = {}
   >
   >* entry：入口文件，需要打包的源文件，,也可以是多个文件,此时output中的filename可以用name外套中括号来表示输出文件名
   >
   >* output：输出文件，打包合并后的目标文件，其中包含path和filename两项
   >
 * 参考代码
 
```  
      module.exports = {
      
      entry:__dirname + '/app/main.js',      
      
      output:{
      
        path:__dirname + '/public',
        
        filename:'webpack.js'
        
      }
     }
 ```
  * 执行打包命令
   `webpack`
   
 3. 使用配置文件打包2，针对没有全局安装webpack的情况
 
 * 按照上面的打包方法1，完成webpack配置文件的内容设置
   
 * 在package.js文件中的script项中添加"start"：“webpack”
 
 * 执行打包命令,npm后面的命令名必须和script中的key保持一致，例如把start改掉，则npm后面start也必须保持一致
 `npm start`
