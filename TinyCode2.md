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

### Windows 10的资源管理器地址栏中输入cmd, 则打开命令行窗口并处于当前路径

### 获取安装的驱动程序信息
driverquery -v

### ip地址管理和查询
ipconfig /release  
ipconfig /renew  
ipconfig /flushdns  
ipconfig /all  ::可查到mac地址，即以太网适配器的物理地址

### 查看网络活动连接，将为您提供当前打开的端口和相关IP地址的列表
netstat -an
netstat -ano|findstr "80" #端口占用查询

### 超级ping，返回一个跃点跟踪列表
```
C:\>pathping qq.com

通过最多 30 个跃点跟踪
到 qq.com [111.161.64.40] 的路由:
  0  xiqi [192.168.0.102]
  1  192.168.0.1
  2  192.168.1.1
  3  10.11.192.1
  4  183.214.234.9
  5     *        *        *
正在计算统计信息，已耗时 100 秒...
```

### Windows命令shutdown的详细用法
```
C:\>shutdown /?
用法: shutdown [/i | /l | /s | /sg | /r | /g | /a | /p | /h | /e | /o] [/hybrid] [/soft] [/fw] [/f]
    [/m \\computer][/t xxx][/d [p|u:]xx:yy [/c "comment"]]

    没有参数   显示帮助。这与键入 /? 是一样的。
    /?         显示帮助。这与不键入任何选项是一样的。
    /i         显示图形用户界面(GUI)。
               这必须是第一个选项。
    /l         注销。这不能与 /m 或 /d 选项一起使用。
    /s         关闭计算机。
    /sg        关闭计算机。在下一次启动时，
               重启任何注册的应用程序。
    /r         完全关闭并重启计算机。
    /g         完全关闭并重新启动计算机。在重新启动系统后，
               重启任何注册的应用程序。
    /a         中止系统关闭。
               这只能在超时期间使用。
               与 /fw 结合使用，以清除任何未完成的至固件的引导。
    /p         关闭本地计算机，没有超时或警告。
               可以与 /d 和 /f 选项一起使用。
    /h         休眠本地计算机。
               可以与 /f 选项一起使用。
    /hybrid    执行计算机关闭并进行准备以快速启动。
               必须与 /s 选项一起使用。
    /fw        与关闭选项结合使用，使下次启动转到
               固件用户界面。
    /e         记录计算机意外关闭的原因。
    /o         转到高级启动选项菜单并重新启动计算机。
               必须与 /r 选项一起使用。
    /m \\computer 指定目标计算机。
    /t xxx     将关闭前的超时时间设置为 xxx 秒。
               有效范围是 0-315360000 (10 年)，默认值为 30。
               如果超时时间大于 0，则默示为
               /f 参数。
    /c "comment" 有关重新启动或关闭的原因的注释。
               最多允许 512 个字符。
    /f         强制关闭正在运行的应用程序而不事先警告用户。
               如果为 /t 参数指定大于 0 的值，
               则默示为 /f 参数。
    /d [p|u:]xx:yy  提供重新启动或关闭的原因。
               p 指示重启或关闭是计划内的。
               u 指示原因是用户定义的。
               如果未指定 p 也未指定 u，则重新启动或关闭
               是计划外的。
               xx 是主要原因编号(小于 256 的正整数)。
               yy 是次要原因编号(小于 65536 的正整数)。
``` 

```
shutdown /h        :: 休眠（hibernate）本地计算机
shutdown /r /o #重启你的电脑进入高级启动选项菜单，你可以在这里访问安全模式和Windows恢复实用程序 
shutdown /s /t 30  ::30秒后关闭计算机
```              

### sfc, System File Checker
sfc, System File Checker是一种自动扫描和修复工具，专注于Windows系统文件

### tasklist 和 taskkill
```
tasklist /svc ::显示与每个任务相关的服务  
tasklist /v   ::详细任务列表  
tasklist /m   ::定位与活动任务相关的DLL文件
TASKKILL /F /IM QQ* /T ::强制结束QQ开头的进程及其子进程
taskkill /F /pid 3328 /pid 3360 /T
```

### 发送消息给局域网内的Windows在线用户
msg /server:192.168.0.102 * "你好,聊会儿吧"

### 显示完整的无线设备和网络信息
netsh wlan show all

netsh(Network Shell) 是一个windows系统本身提供的功能强大的网络配置命令行工具

### Windows用户管理命令，黑客必知必会
```
net user cody 123456 /add
net user cody localgroup Administrators
net user cody /ACTIVE:YES
net user cody 654321  :: 把cody的密码改为654321
net user John /delete
```

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

    $ cd F:\cloud\nwjs\  
    $ D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe livemark

提示: Windows中，你可以把包含package.json的文件夹拖到nw.exe上来运行
还可以把应用打包后再运行

    "C:\Program Files\7-Zip\7z.exe" a livemark.zip .\livemark\*
    D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe  livemark.zip
    ren livemark.zip livemark.nw
    D:\app\nwjs-sdk-v0.38.3-win-x64\nw.exe  livemark.nw

#### 发布应用
注意到 D:\app\nwjs-v0.38.3-win-x64\目录下也有一个package.json, 它是不带参数运行nw.exe时打开的缺省应用，因此可以将自己的应用合并到nwjs目录下重命名后再次发布。  
还可以将两个文件合并以后再发布
`> copy /b nw.exe+app.nw app.exe `
Linux中合并的命令行为:
`> cat `which nw` app.nw > app && chmod +x app `

具体细节可参考官方文档 https://github.com/nwjs/nw.js/wiki/How-to-package-and-distribute-your-apps


### Javascript Tricks and Bookmarklets 

```
// 一些最基本的Javascript技巧
    !!foo //转为bool值
    ~~2.235 // 2，取整，~ 是按位取非运算符
    ~~-2.235 // -2
    Math.floor(-2.235) // -3
    ~~ "-3.05" // -3 ， 这里~~代替了parseInt的作用
    ~~ "3.2E10" // 1935228928
    +"-12.56"   // -12.56 ， parseInt
    +!![]       // 1 , +!![]===+true===1
    v=[] && 10  // 10
    v=[] || 10  // []

// 创建过去七天的数组
[...Array(7).keys()].map(days => new Date(Date.now() - 86400000 * days));

// 生成长度为11的随机字母数字字符串
Math.random().toString(36).substring(2);
// 4yzqwrvw9iu

//获取URL的查询参数
//?foo=bar&baz=bing => {foo: bar, baz: bing}
q={};location.search.replace(/([^?&=]+)=([^&]+)/g,(_,k,v)=>q[k]=v);q;

//网页上显示本地时间
<span id="timebar"></span>
<script>setInterval(()=>document.getElementById("timebar").innerHTML=new Date().toLocaleString()/*.slice(10,19)*/) </script>

//混淆数组shuffle
arr=[...Array(7).keys()]
arr.slice().sort(() => Math.random() - 0.5)

// 生成随机十六进制颜色代码 如：'#c618b2'
'#' + Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, '0');

// 数组去重
[...new Set(arr)]

// 用字符串返回一个键盘图形

(_=>[..."`1234567890-=~~QWERTYUIOP[]\\~ASDFGHJKL;'~~ZXCVBNM,./~"].map(x=>(o+=`/${b='_'.repeat(w=x<y?2:' 667699'[x=["BS","TAB","CAPS","ENTER"][p++]||'SHIFT',p])}\\|`,m+=y+(x+' ').slice(0,w)+y+y,n+=y+b+y+y,l+=' __'+b)[73]&&(k.push(l,m,n,o),l='',m=n=o=y),m=n=o=y='|',p=l=k=[])&&k.join`

`)()

```

