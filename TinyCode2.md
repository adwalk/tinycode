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


HTML&Javascript&CSS
----

### 在Chrome Developer tools 或者 Firefox Devtools的控制台中做Ajax请求
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

### Javascript bookmarklets
