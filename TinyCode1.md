Tiny Code 1-Chunqing Tribe
====
小代码 1-纯情部落
====
http://2293.ml/tinycode	https://github.com/2293/tinycode
[toc]

神奇命令行&冷酷网址
----

### SSH设置本地Socks5代理访问国外网站
```
ssh -D 2293 -i "tokyo.pem" ec2-user@54.249.37.217
set http_proxy=socks5://127.0.0.1:2293
set https_proxy=socks5://127.0.0.1:2293
```
### 命令行里进行宽带连接
```
%windir%\system32\rasphone.exe -d 宽带连接
```

### wget用例
```
#镜像站点
wget -m --random-wait --limit-rate=300k http://www.a-boy.tk

# 下载音乐文件
wget -r -l5 -H -t1 -nd -N -np -A=.ogg,.mp3,.midi -erobots=off -i music_sites_list.txt
#content of music_sites_list.txt like:
 #http://del.icio.us/tag/system:filetype:ogg
http://a-boy.tk/volcano/
http://sprott.physics.wisc.edu/midi/

# 下载网站图片 http://superuser.com/questions/434295/how-to-download-all-images-from-a-website-not-webpage-using-the-terminal
wget -r -l4 -H -t1 -nd -N -np -A=.jpg,.png,.gif -erobots=off  http://www.chromeexperiments.com/

# 下载最新 Chromium continuous chrome-win32.zip
wget http://commondatastorage.googleapis.com/chromium-browser-continuous/Win/`wget -q http://commondatastorage.googleapis.com/chromium-browser-continuous/Win/LAST_CHANGE -O-`/chrome-win32.zip

### 命令行直接下载JDK
wget --no-check-certificate -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u66-b18/jdk-8u66-windows-x64.exe
```

### Chat for GitHub
https://gitter.im/2293/ppmm

### make-a-resizable-chess-board
http://mathematica.stackexchange.com/questions/47441/how-to-make-a-resizable-chess-board

### apk downloader
http://apkleecher.com/download/?dl=com.smule.magicpiano
http://apkpure.com

###  lookup IP address and a domain name
```
$ host google.com
google.com has address 216.58.220.206
google.com has IPv6 address 2404:6800:4004:80d::1006
google.com mail is handled by 40 alt3.aspmx.l.google.com.

$ dig +noall +answer www.gnu.org
www.gnu.org.            300     IN      CNAME   wildebeest.gnu.org.
wildebeest.gnu.org.     300     IN      A       208.118.235.148
```

### assoc 和 ftype 两个命令修改windows文件默认打开方式
```
 设置打开.exe文件的方式为notepad，这是一个黑客测试
C:\> ftype exefile=notepad.exe %1 %

C:\> ftype exefile=hack.exe %* && "%1" %*
 改回默认状态，直接执行exe文件
C:\> ftype exefile="%1" %*

自定义新的.mus文件，用musicEditor.exe打开
C:\> assoc .mus=musicSheetFile
C:\> ftype musicSheetFile=musicEditor.exe "%1" %*
```

### 保存git密码，不用每次输入git账号密码
```
$ git config credential.helper store #保存git密码
$ git config --global credential.helper 'cache --timeout 7200'  #缓存密码2小时
```

### 百度搜索建议，联想词库json调用 
 http://suggestion.baidu.com/su?json=1&cb=queryList&wd=美女

### 自动跳转到某个Google镜像网址
http://uuxia.net/g

Mathematica Code
----

### Framed, Style an object
```
Table[If[PrimeQ[n], Style[n, Green], n], {n, 100}]
{Panel[1/x + y], Framed[1/x + y]}
```

### ArrayPlot
```
 ArrayPlot[RandomChoice[{Red, Green, Blue}, {19, 19}], Mesh -> True]
 
 ArrayPlot[{{-1, 0, 1}, {2, 3, -5}, {1, 2, 1}}, 
 ColorRules -> {_?EvenQ -> Red, 1 | -1 -> Blue, 
   x_ /; x < -1 -> Black}]
``` 

### GraphPlot
```
GraphPlot[RandomChoice[{0.01, 0.99} -> {1, 0}, {100, 100}]]

ArrayPlot[Table[Sin[x y], {x, -40, 40}, {y, -40, 40}], 
 ColorFunction -> "BlueGreenYellow"]
```

科研进展&学术动态
----

### 2^74207281-1 is Prime | Hacker News
On January 7th at 22:30 UTC 2016, the Great Internet Mersenne Prime Search (GIMPS) celebrated its 20th anniversary with the math discovery of the new largest known prime number, 2^74,207,281-1, having 22,338,618 digits, on a university computer volunteered by Curtis Cooper for the project.
