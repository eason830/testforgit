# Babel how to use
## 自學使用
## 原作者 from:https://juejin.cn/post/7147582343471955999
## 用途可以把 ES6 轉成 ES5，支援舊的瀏覽器
### babel 7 的開頭是 @babel/， babel 6 是 babel-core
### 使用 babel 一定要有配置文件 ex: babel.config.js
```js
module.exports = {
  presets:[],
  plugins:[]
}
```
     presets 稱為預設數組
     plugins  稱為插件數組
---
## 實例演示
### 創一個 babel_test 資料夾
### 裡面新增 before.js 、 babel.config.js
### 先 npm init 初始化 package.json
    before.js
        裡面寫一些 ES6

    babel.config.js
        module.exports = {
          presets:[],
          plugins:[]
        }
### 安裝必要的 npm
### @babel/core為核心包，@babel/cli為解析命令行的包
      npm install @babel/core @babel/cli -D
### 在 package.json 設置一條指令
### 把 before.js 經過 babel 後，輸出創建 after.js
      "scripts":{
        "babel":"babel before.js -o after.js"
      }
### 目前只是原封不動輸出到 after.js
---
## 插件基本使用
### 裝插件 => 轉換箭頭函數語法
    npm install @babel/plugin-transform-arrow-functions -D
### 安裝好，在 babel.config.js 進行配置
      module.exports = {
        presets: [],
        plugins: ["@babel/plugin-transform-arrow-functions"]
      }
### 執行 npm run babel => 即可以知道 配置的插件 有沒有成功
### 成功則 箭頭函式 則會被轉換
---
### 插件只能轉譯某一種語法
### 轉譯可選鏈
    npm install @babel/plugin-proposal-optional-chaining -D
    module.exports = {
      presets: [],
      plugins: ["@babel/plugin-transform-arrow-functions",
      "@babel/plugin-proposal-optional-chaining"]
    }
---
     如果有很多種語法要轉譯就要有很多插件
     解決辦法就是 presets 的使用
# 預設(presets)的基本使用
## presets等同插件集合

<br>

### 一樣先安裝 npm 預設包
    npm install @babel/preset-env -D
### 設置 babel.config.js
    module.exports = {
      presets: ["@babel/preset-env"],
      plugins: []
    }
### 就可以執行 npm run babel
---
## 如果以 vue 開發
### 預設就只需要安裝 @babel/preset-env
### 插件只需要 @babel/plugin-transform-runtime
## 預設與插件處理順序(當處理同一程式碼)
    1.插件比預設先執行
    2.插件plugins陣列 從前到後執行
    3.預設presets陣列 從後向前執行
---
# 什麼是 polyfill (概念與使用方法)
## polyfill就是為了轉譯 ES6高版本的API
### 理解就是有些 babel env 沒有轉譯的 新的 API，
### 就要使用 polyfill 去轉譯
---
