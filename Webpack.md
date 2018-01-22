# Webpack应用
## 一、Webpack概述
   
   > Webpack是一个模块加载器以及打包工具，能把各种资源，例如js、样式和图片等作为模块进行使用和处理。
   
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
   
 2. 利用配置文件进行打包
 
     A. 项目根路径下添加webpack.config.js配置文件
     
     B. 在配置文件中，添加配置代码
     
     C. 自动运行
     
    
