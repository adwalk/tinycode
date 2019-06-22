Tiny Code 2-Coming from Wave
====
小代码 2-浪沫迩来
====

又名 《火星人学习报》第2期 代号:浪沫迩来 2019年6月

http://2293.ml/tinycode/
https://github.com/2293/tinycode/

[toc]

人物风云
----


神奇命令行&冷酷网址
----
自由钢琴  http://www.autopiano.cn  
纯情部落  http://2293.ml  

HTML&Javascript&CSS
----

### 用fetch在Chrome DevTools 或者 Firefox Devtools的控制台中做Ajax请求
```
//To GET a text file:
fetch('http://a-boy.tk')
  .then(res => res.text())
  .then(console.log)

// Example POST method implementation:
postData('http://example.com/answer', {answer: 42})
  .then(data => console.log(JSON.stringify(data))) // JSON-string from `response.json()` call
  .catch(error => console.error(error));

function postData(url = '', data = {}) {
  // Default options are marked with *
    return fetch(url, {
        method: 'POST', // *GET, POST, PUT, DELETE, etc.
        mode: 'cors', // no-cors, cors, *same-origin
        cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
        credentials: 'same-origin', // include, *same-origin, omit
        headers: {
            'Content-Type': 'application/json',
            // 'Content-Type': 'application/x-www-form-urlencoded',
        },
        redirect: 'follow', // manual, *follow, error
        referrer: 'no-referrer', // no-referrer, *client
        body: JSON.stringify(data), // body data type must match "Content-Type" header
    })
    .then(response => response.json()); // parses JSON response into native Javascript objects 
}

//Chrome Devtools 现在支持一种新的async/await 语法
const response = await fetch('http://2293.ml/tinycode/TinyCode1.md')
console.log(await response.text())
//记得你的请求应该遵从同源策略(same-origin policy)
```

### 快速掌握nw.js(node-webkit)开发桌面应用
https://github.com/nwjs/nw.js  
Official site: https://nwjs.io  

#### 快速入门

新建文件 index.html:
```
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>livemark</title>
</head>
<body>
    We are using node.js <script>document.write(process.version)</script><br>
    <input type="text" name="edit1" id="edit1" value="2293.ml">    
</body>
</html>
```

新建文件 package.json:
```
{
  "name": "livemark",
  "version": "0.0.1",
  "main": "index.html"
}
```

假设这两个文件放在F:\cloud\nwjs\livemark\ 目录下，然后运行:

    $ cd F:\cloud\nwjs\livemark\  
    $ D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe .

提示: Windows中，你可以把包含package.json的文件夹拖到nw.exe上来运行
还可以把应用打包后再运行

    "C:\Program Files\7-Zip\7z.exe" a livemark.zip .\livemark\*
    D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe  livemark.zip
    ren livemark.zip livemark.nw
    D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe  livemark.nw

#### 发布应用
注意到 D:\app\nwjs-v0.38.3-win-x64\目录下也有一个package.json, 它是不带参数运行nw.exe时打开的缺省应用，因此可以将自己的应用合并到nwjs目录下重命名后再次发布。  
还可以将两个文件合并以后再发布
> copy /b nw.exe+app.nw app.exe 
Linux中合并的命令行为:
> cat `which nw` app.nw > app && chmod +x app 

具体细节可参考官方文档 https://github.com/nwjs/nw.js/wiki/How-to-package-and-distribute-your-apps




### Javascript bookmarklets
