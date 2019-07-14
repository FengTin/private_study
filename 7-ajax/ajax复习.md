```
ajax:阿贾克斯。
传统网站的劣势：
    1.加载速度慢
    2.每次刷新重新刷新整个页面
    3.表单验证（用户体验不好）
ajax：
    什么是ajax
        1.交互式的网站开发技术
        2.实现动态更新（局部）的内容
    为什么使用ajax（能给开发带来什么样的帮助）
        优点：
            1.提升浏览器的加载速度
            2.实现了局部刷新
            3.表单验证（增强用户体验）
    ajax的应用场景
        1.表单验证
        2.局部加载更多
        3.不跳转页面的情况下  某一个地方更新。
    ajax怎么用：
    get:
        1.创建异步对象( 就可以发送异步请求)
            var xhr = new XMLHttpRequest()；
        2.告诉ajax 请求的方式  请求的地址
            xhr.open("请求方式","请求地址")
        3.设置请求体：
            xhr.send(null);
            监听ajax的动态
        4.xhr.onreadystatechange = function(){
            等到浏览器返回成功并且 解析完毕
            if(xhr.status==200 && xhr.readystate==4){
                console.log(xhr.responseText)
            }
        }
   注意点：
        ajax是异步请求
        ajax 必须有服务器的
    原理：
      早起：  浏览器----->服务器  不可控
      ajax:  浏览器---->ajax----->服务器 可控

    json：  描述数据的一种数据。

    跨域： 
        浏览器的同源策略
            域名  协议  端口 有一个不同那么浏览器阻止返回内容。。
        浏览器阻止什么：
            ？？？？？
        跨域请求：  src   href  link；
       jsonp:
            原理： 利用src跨域的特性所以动态创建script src去请求资源
            实现方式：
               1. 先定义一个函数  然后动态创建script标签利用src特性请求资源
               2. 在请求地址后面需要加参数（ 参数名=函数名）
               3.后台拿到函数名  在以函数名调用的形式返回
               4.拿到数据直接调用
            前台：  
                
        var script = document.createElement("script");
        script.type = "text/javascript";
        script.src = "http://www.day2.com/data.php?call=fn";
        document.head.appendChild(script);
        后台：  
             $num = 10;
            $callback =  $_GET["call"];
            echo $callback.'('.$num.')';
        jq：
            默认的是callback
            dataType: "jsonp",  利用jsonp的原理
            jsonp: "call",更改默认的callback
        cors：跨域资源共享
            原理： 
                请求发送---浏览器阻止---发送预信息（网站域名）----后台拿到域名（后台考虑是否给你（header("Access-Control-Allow-Origin:*")））  ----浏览器
                ----（自动识别（服务器允许跨域））----返回客户端数据
            允许所有的网址请资源
                 header("Access-Control-Allow-Origin:*");
        3.服务器代理：（服务器之间不存在跨域）
            服务器的反向代理：

```

