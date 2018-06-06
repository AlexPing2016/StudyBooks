# Webpack应用
## 一、Webpack概述(针对4.1版本)
Webpack是一个模块加载器以及打包工具，能把各种资源，例如js、样式和图片等作为模块进行使用和处理。
   
* 支持CommonJS（服务器端为主，主要应用是nodeJS和webpack）和AmdJS（浏览器端应用，解决CommonJS同步加载缓慢的问题）
* 支持其他模块的加载器，例如babel
* 通过配置打包多个文件
* 支持SCSS,SASS样式文件预处理，和图片资源等的打包  
## 二、安装

1. 安装nodejs
2. 全局安装
 
  ```
   npm install -g webpack  
   npm install -g webpack-cli
  ```
  
3. 项目文件夹初始化

  `npm init`
  
4. 项目文件夹中安装
 
  ```
   npm install webpack -S
   npm install webpack-cli -S
   ```
    
## 三、基本应用

1. 打包文件的基本方法(默认方式打包js文件，可不做配置)  
 
  ```
   webpack  源文件  目标文件(老版本使用)
   webpack (4.1版本使用，使用默认的入口和出口文件路径)
   webpack  --mode production（生产模式，一行显示）
   webpack  --mode development（开发模式，多行显示）
  ```
   
2. 利用配置文件进行打包方式
 
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
   
 3. 修改执行打包命令方式
 
 * 按照上面的打包方式1，先完成webpack配置文件的内容设置
   
 * 在package.js文件中的script项中添加子项"start"：“webpack”,当npm启动时会执行webpack打包命令
   
   ```
    scripts:{
      start:"webpack"
    }
    ====================
    执行打包命令：npm start
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

2. 加载CSS样式文件
  
  * 安装style-loader和css-loader
  * 在webpack配置文件中，添加模块配置项
  * 在调用的js文件中通过require加载样式文件
  
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

3. ES6转换
