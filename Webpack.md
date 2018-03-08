# Webpack应用
## 一、Webpack概述(针对3.1版本)
Webpack是一个模块加载器以及打包工具，能把各种资源，例如js、样式和图片等作为模块进行使用和处理。
   
* 支持CommonJS（服务器端为主，主要应用是nodeJS和webpack）和AmdJS（浏览器端应用，解决CommonJS同步加载缓慢的问题）
* 支持其他模块的加载器，例如babel
* 通过配置打包多个文件
* 支持SCSS,SASS样式文件预处理，和图片资源等的打包
## 二、安装

1. 安装nodejs
2. 全局安装webpack-cli
 
  `npm install -g webpack-cli`
  
3. 项目文件夹初始化
 
  `npm init`
  
4. 项目文件夹中安装webpack-cli
 
  `npm install webpack-cli -D`
    
## 三、基本应用

1. 打包文件的基本方法
 
  `webpack  源文件  目标文件(新版本不支持)`
   
2. 利用配置文件进行打包方式1（全局安装webpack的情况下）
 
 * 项目根路径下添加webpack.config.js配置文件
 * 在上述配置文件中，添加配置项 

   + module.exports = {} 
   
   + entry：入口文件,需要打包的源文件,也可以是多个文件,此时output中的filename可以用name外套中括号来表示输出文件名 
   
   + output：输出文件，打包合并后的目标文件，其中包含path和filename两项 


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
    
    ```webpack```
   
 3. 使用配置文件打包方式2(没有全局安装webpack的情况)
 
 * 按照上面的打包方式1，先完成webpack配置文件的内容设置
   
 * 在package.js文件中的script项中添加子项"start"：“webpack”,当npm启动时会执行webpack打包命令
   
   ```
    scripts:{
      start:"webpack"
    }
    npm start
   ```
 
 * 如果把start改为hd，则要用npm run hd
 

## 四、高级应用

1. 加载json文件

* 安装json-loader模块

* 在webpack配置文件中，添加模块配置项

```
  module:{
  
        loaders:[
        
            {
            
                test:/\.json$/,//test设置文件格式的正则表达式
                
                use:"json-loader"//use设置加载的类型
                
            }
        ]
    }

```

* 在调用的js文件中通过require加载json文件

2. CSS样式文件
  
  * 安装style-loader和css-loader
  
  * 在webpack配置文件中，添加模块配置项
  ```
    module: {
        rules: {
        {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      }
    ]
  }
  ```
  * 在调用的js文件中通过require加载样式文件

3. ES6转换
