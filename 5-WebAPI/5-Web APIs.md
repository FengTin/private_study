# 一 Web APIs第一天

## 1 获取元素

### 1.1 根据ID获取

```html
        
	<div id='time'>2019-6-17</div>
    <div id='date'>2015-5-17</div>
    <div id='money'>23￥</div>
    <script>
        // document.getElementById(id)
        // 1. 因为我们文档页面从上往下加载，所以先得有标签 所以我们script写到标签的下面
        // 2. get 获得 element 元素 by 通过 驼峰命名法 
        // 3. 参数 id是大小写敏感的字符串
        // 4. 返回的是一个元素对象
        var timer = document.getElementById('time');
        console.log(timer);
        // 5. console.dir 打印我们返回的元素对象 更好的查看里面的属性和方法
        console.dir(timer);

        var dater = document.getElementById('date');
        console.log(dater);
        console.dir(dater);

        var moneyr = document.getElementById('money');
        console.log(moneyr);
        console.dir(moneyr);
    </script>
```

### 1.2 根据标签名获取

```html
<body>
    <ul>
        <li>好好学习，天天向上1</li>
        <li>好好学习，天天向上</li>
        <li>好好学习，天天向上</li>
        <li>好好学习，天天向上</li>
        <li>好好学习，天天向上</li>
    </ul>
    <ol id='ol'>
        <li>good good study , day day up</li>
        <li>good good study , day day up</li>
        <li>good good study , day day up</li>
        <li>good good study , day day up</li>
        <li>good good study , day day up</li>
    </ol>
    <script>
        // 1 返回的是页面中的所有元素
        var lis = document.getElementsByTagName('li');
        // console.log(lis);
        // console.log(lis[0]);
        // 2. 我们想要依次打印里面的元素对象我们可以采取遍历的方式
        for (var i = 0; i < lis.length; i++) {
            console.log(lis[i]);

        }
        // 3. 如果页面中只有一个li 返回的还是伪数组的形式 
        // 4. 如果页面中没有这个元素 返回的是空的伪数组的形式

        // 5. element.getElementsByTagName('标签名'); 父元素必须是指定的单个元素
        var ol = document.getElementById('ol');
        console.log(ol.getElementsByTagName('li'));
    </script>
</body>
```

### 1.3 H5新增获取元素方式

```html
<body>
    <div class="box">盒子1</div>
    <div class="box">盒子2</div>
    <div id="nav">
        <ul>
            <li>盒子3</li>
            <li>盒子4</li>
        </ul>
    </div>

    <script>
        // 1. getElementsByClassName 根据类名获得某些元素集合  不常用
        var boxs = document.getElementsByClassName('box');
        console.log(boxs);

        // 2. querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav
        var firstBox = document.querySelector('.box');
        console.log(firstBox);
        var nav = document.querySelector('#nav');
        console.log(nav);
        var lis = document.querySelector('#nav ul li'); // css里面的选择器都可以用，比如 .box ul li 或者.box,ul ,交集 并集 后代等选择器均可以使用
        console.log(lis);
        // 3. querySelectorAll()返回指定选择器的所有元素对象集合
        var allBox = document.querySelectorAll('.box');
        console.log(allBox);
        var allLi = document.querySelectorAll('ul li');
        console.log(allLi);
    </script>
</body>
```

### 1.4 获取特殊元素(body html)

```js
	    // 1.获取body 元素
        var bodyEle = document.body;
        console.log(bodyEle);
        console.dir(bodyEle);
        // 2.获取html 元素
        // var htmlEle = document.html;
        var htmlEle = document.documentElement;
        console.log(htmlEle);
```

## 2 事件

### 2.1 事件三要素

- 事件源（谁）：触发事件的元素
- 事件类型（什么事件）： 例如 click 点击事件
- 事件处理程序（做啥）：事件触发后要执行的代码(函数形式)，事件处理函数

```html
<body>
    <button id="btn">天王</button>
    <p class="ta">唐伯虎</p>
    <script>
        // 点击一个按钮，弹出对话框
        // 1. 事件是有三部分组成  事件源  事件类型  事件处理程序   我们也称为事件三要素
        //(1) 事件源 事件被触发的对象   谁  按钮
        var bt = document.querySelector('#btn');
        //(2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
        //(3) 事件处理程序  通过一个函数赋值的方式 完成
        bt.onclick = function() {
            alert('盖地虎');
        }

        var tang = document.querySelector('.ta');
        tang.onclick = function() {
            alert('点秋香');
        }
    </script>
</body>
```

![cursor-click](E:\2-就业班视频\综合笔记\images\cursor-click.png)

## 3 操作元素

### 3.1 innerText和innerHTML的区别（改变元素的内容）

```html
<body>
    <div></div>
    <p>
        我是文字
        <span>123</span>
    </p>

    <script>
        // innerText 和 innerHTML的区别 
        // 1. innerText 不识别html标签 非标准  去除空格和换行
        var div = document.querySelector('div');
        // div.innerText = '<strong>今天是：</strong> 2019';
        // 2. innerHTML 识别html标签 W3C标准 保留空格和换行的
        div.innerHTML = '<strong>今天是：</strong>2019年5月17日';
        // 这两个属性是可读写的  可以获取元素里面的内容
        var p = document.querySelector('p');
        console.log(p.innerText);
        console.log(p.innerHTML);
    </script>
</body>
```

### 3.2 修改元素

```html
<body>
    <button id="ldh">刘德华</button>
    <button id="zxy">张学友</button> <br>
    <img src="images/ldh.jpg" alt="" title="刘德华">
    <div>
        <img src="images/z.gif" alt="">
    </div>

    <script>
        var ldh = document.querySelector('#ldh');
        var zxy = document.querySelector('#zxy');
        var img = document.querySelector('img');
        var img1 = document.querySelector('div img');
        ldh.onclick = function() {
            img.src = 'images/ldh.jpg';
            img.title = '刘德华';
        }
        zxy.onclick = function() {
            img.src = 'images/zxy.jpg';
            img.title = '张学友';
        }
    </script>
</body>
```

### 3.3 分时问候案例

```html
<body>
    <img src="images/s.gif" alt="">
    <div>上午好</div>
    <script>
        // 根据系统不同时间来判断，所以需要用到日期内置对象
        // 利用多分支语句来设置不同的图片
        // 需要一个图片，并且根据时间修改图片，就需要用到操作元素src属性
        // 需要一个div元素，显示不同问候语，修改元素内容即可
        // 1.获取元素
        var img = document.querySelector('img');
        var div = document.querySelector('div');
        // 2. 得到当前的小时数
        var date = new Date();
        var h = date.getHours();
        // 3. 判断小时数改变图片和文字信息
        if (h < 12) {
            img.src = 'images/s.gif';
            div.innerHTML = '亲，上午好，好好写代码';
        } else if (h < 18) {
            img.src = 'images/x.gif';
            div.innerHTML = '亲，下午好，好好写代码';
        } else {
            img.src = 'images/w.gif';
            div.innerHTML = '亲，晚上好，好好写代码';

        }
    </script>
</body>
```

### 3.4 表单元素的属性

```html
<body>
    <button>按钮</button>
    <input type="text" value="输入内容">
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var input = document.querySelector('input');
        // 2. 注册事件 处理程序

        // input.innerHTML = '点击了';  这个是 普通盒子 比如 div 标签里面的内容
        // 表单里面的值 文字内容是通过 value 来修改的

        // 如果想要某个表单被禁用 不能再点击 disabled  我们想要这个按钮 button禁用
        // btn.disabled = true;


        btn.onclick = function() {
            input.value = '被点击了';
            // 禁用按钮
            // btn.disabled = true;
            this.disabled = true;
            // 1 事件操作中， this 指向的是事件函数的调用者 btn

            function People(uname, sex, age) {
                this.name = uname;
                this.sex = sex;
                this.age = age;
                this.skill = function(sing) {
                    console.log(sing);
                }
            }
            var ldh = new People('刘德华', '男', 18, );
            console.log(ldh.name);
            console.log(ldh.sex);
            console.log(ldh.age);
            ldh.skill('冰雨');
            var gfc = new People('郭富城', '男', 19);
            console.log(gfc.name);
            console.log(gfc.sex);
            console.log(gfc.age);
            gfc.skill('郭富城')
                // 2  在构造函数中,this指向的是new出来的那个实例对象；
        }
    </script>
</body>
```

### 3.5 仿京东开关

```html
<body>
    <div class="box">
        <label for="">
            <img src="images/close.png" alt="" id="eye">
        </label>
        <input type="password" name="" id="pwd">
    </div>
    <script>
        // 1 获取元素
        var eye = document.querySelector('#eye');
        var pwd = document.querySelector('#pwd');

        var flag = 0;
        eye.onclick = function() {
                // 点击一次之后，flag一定要变化
                if (flag == 0) {
                    eye.src = 'images/open.png';
                    pwd.type = 'text';
                    flag = 1; // 赋值操作
                } else {
                    pwd.type = 'password';
                    eye.src = 'images/close.png';
                    flag = 0;
                }

            }
            // flag 相当于开关
    </script>
</body>
```

### 3.6 改变样式属性

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .box1 {
            position: absolute;
            left: 0;
            width: 200px;
            height: 200px;
            background-color: pink;
            transition: all .5s linear;
        }
        
        .box2 {
            left: 500px;
        }
    </style>
</head>

<body>
    <div class="box1"></div>
    <script>
        // 1. 获取元素
        var div = document.querySelector('div');
        // 2. 注册事件 处理程序
        div.onclick = function() {
            // div.style里面的属性 采取驼峰命名法 
            this.style.width = '300px';
            this.style.backgroundColor = 'purple';
            this.className = 'box1 box2'; // 如果有两个类名，则需写上两个类名，重新赋值
        }
    </script>
</body>
```

### 3.7 循环精灵图

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        li {
            list-style-type: none;
        }
        
        .box {
            width: 250px;
            margin: 100px auto;
        }
        
        .box li {
            float: left;
            width: 24px;
            height: 24px;
            background-color: pink;
            margin: 15px;
            background: url(images/sprite.png) no-repeat;
        }
    </style>
</head>

<body>
    <div class="box">
        <ul>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>
    <script>
        // 1. 获取元素 所有的小li 
        var lis = document.querySelectorAll('li');

        // 让索引号 乘以 44 就是每个li 的背景y坐标  index就是我们的y坐标
        for (var i = 0; i < lis.length; i++) {
            var index = i * 44;
            lis[i].style.backgroundPosition = `0 -${index}px`;
        }
    </script>
</body>

```

### 3.8 仿京东-搜索框案例

```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        input {
            color: #999;
        }
    </style>
</head>

<body>
    <input type="text" value="手机">
    <script>
        // 1.获取元素
        var text = document.querySelector('input');
        // 2.注册事件 获得焦点事件 onfocus 
        text.onfocus = function() {
            this.style.color = '#333';
            if (this.value === '手机') {
                this.value = '';
            }

        }
        text.onblur = function() {
            this.style.color = '#999';
            if (this.value === '') {
                this.value = '手机';
            }
        }
    </script>
</body>
```

### 3.9 仿新浪注册页面

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 600px;
            margin: 100px auto;
        }
        
        .message {
            display: inline-block;
            font-size: 12px;
            color: #999;
            background: url(images/mess.png) no-repeat left center;
            padding-left: 20px;
        }
        
        .wrong {
            color: red;
            background-image: url(images/wrong.png);
        }
        
        .right {
            color: green;
            background-image: url(images/right.png);
        }
    </style>
</head>

<body>
    <div class="register">
        <input type="password" class="ipt" value="">
        <p class="message">请输入6~16位密码</p>
    </div>
    <script>
        // 首先判断的事件是表单失去焦点 onblur
        // 如果输入正确则提示正确的信息颜色为绿色小图标变化
        // 如果输入不是6到16位，则提示错误信息颜色为红色 小图标变化
        // 因为里面变化样式较多，我们采取className修改样式
        // 1.获取元素
        var ipt = document.querySelector('.ipt');
        var message = document.querySelector('.message');

        //2. 注册事件 失去焦点
        ipt.onblur = function() {
                if (this.value.length < 6 || this.value.length > 16) {
                    message.className = 'message wrong';
                    message.innerHTML = '您输入的数不是6-16位，请重新输入';
                } else {
                    message.className = 'message right';
                    message.innerHTML = '您输入正确'
                }
            }
            // 根据表单里面值的长度 ipt.value.length
    </script>
</body>

```

# 二  Web APIs第二天

## 1 排他思想

```html
<body>
    <button>按钮1</button>
    <button>按钮2</button>
    <button>按钮3</button>
    <button>按钮4</button>
    <button>按钮5</button>
    <script>
        // 1. 获取所有按钮元素
        var btns = document.getElementsByTagName('button');
        // btns得到的是伪数组  里面的每一个元素 btns[i]
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                // (1) 我们先把所有的按钮背景颜色去掉  干掉所有人
                for (var i = 0; i < btns.length; i++) {
                    btns[i].style.backgroundColor = '';
                }
                // (2) 然后才让当前的元素背景颜色为pink 留下我自己
                this.style.backgroundColor = 'pink';

            }
        }
        //2. 首先先排除其他人，然后才设置自己的样式 这种排除其他人的思想我们成为排他思想
    </script>
</body>
```

## 2 百度换肤案例

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        body {
            background: url(images/1.jpg) no-repeat center top;
        }
        
        li {
            list-style: none;
        }
        
        .baidu {
            overflow: hidden;
            margin: 100px auto;
            background-color: #fff;
            width: 410px;
            padding-top: 3px;
        }
        
        .baidu li {
            float: left;
            margin: 0 1px;
            cursor: pointer;
        }
        
        .baidu img {
            width: 100px;
        }
    </style>
</head>

<body>
    <ul class="baidu">
        <li><img src="images/1.jpg"></li>
        <li><img src="images/2.jpg"></li>
        <li><img src="images/3.jpg"></li>
        <li><img src="images/4.jpg"></li>
    </ul>
    <script>
        // 1. 获取元素 
        var imgs = document.querySelector('.baidu').querySelectorAll('img');
        // console.log(imgs);
        // 2. 循环注册事件 
        for (var i = 0; i < imgs.length; i++) {
            imgs[i].onclick = function() {
                // this.src 就是我们点击图片的路径   images/2.jpg
                // console.log(this.src);
                // 把这个路径 this.src 给body 就可以了
                document.body.style.backgroundImage = 'url(' + this.src + ')';
            }
        }
    </script>
</body>
```

## 3 隔行换色

```html
<style>
        table {
            width: 800px;
            margin: 100px auto;
            text-align: center;
            border-collapse: collapse;
            font-size: 14px;
        }
        
        thead tr {
            height: 30px;
            background-color: skyblue;
        }
        
        tbody tr {
            height: 30px;
        }
        
        tbody td {
            border-bottom: 1px solid #d7d7d7;
            font-size: 12px;
            color: blue;
        }
        
        .bg {
            background-color: pink;
        }
    </style>
</head>

<body>
    <table>
        <thead>
            <tr>
                <th>代码</th>
                <th>名称</th>
                <th>最新公布净值</th>
                <th>累计净值</th>
                <th>前单位净值</th>
                <th>净值增长率</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
            <tr>
                <td>003526</td>
                <td>农银金穗3个月定期开放债券</td>
                <td>1.075</td>
                <td>1.079</td>
                <td>1.074</td>
                <td>+0.047%</td>
            </tr>
        </tbody>
    </table>
    <script>
        // 1.获取元素 获取的是 tbody 里面所有的行
        var trs = document.querySelector('tbody').querySelectorAll('tr');
        // 2. 利用循环绑定注册事件
        for (var i = 0; i < trs.length; i++) {
            // 3. 鼠标经过事件 onmouseover
            trs[i].onmouseover = function() {
                    // console.log(11);
                    this.className = 'bg';
                }
                // 4. 鼠标离开事件 onmouseout
            trs[i].onmouseout = function() {
                this.className = '';
            }
        }
    </script>
</body>
```

## 4 全选反选

```html
 <style>
        * {
            padding: 0;
            margin: 0;
        }
        
        .wrap {
            width: 300px;
            margin: 100px auto 0;
        }
        
        table {
            border-collapse: collapse;
            border-spacing: 0;
            border: 1px solid #c0c0c0;
            width: 300px;
        }
        
        th,
        td {
            border: 1px solid #d0d0d0;
            color: #404060;
            padding: 10px;
        }
        
        th {
            background-color: #09c;
            font: bold 16px "微软雅黑";
            color: #fff;
        }
        
        td {
            font: 14px "微软雅黑";
        }
        
        tbody tr {
            background-color: #f0f0f0;
        }
        
        tbody tr:hover {
            cursor: pointer;
            background-color: #fafafa;
        }
    </style>

</head>

<body>
    <div class="wrap">
        <table>
            <thead>
                <tr>
                    <th>
                        <input type="checkbox" id="j_cbAll" />
                    </th>
                    <th>商品</th>
                    <th>价钱</th>
                </tr>
            </thead>
            <tbody id="j_tb">
                <tr>
                    <td>
                        <input type="checkbox" />
                    </td>
                    <td>iPhone8</td>
                    <td>8000</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox" />
                    </td>
                    <td>iPad Pro</td>
                    <td>5000</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox" />
                    </td>
                    <td>iPad Air</td>
                    <td>2000</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox" />
                    </td>
                    <td>Apple Watch</td>
                    <td>2000</td>
                </tr>

            </tbody>
        </table>
    </div>
    <script>
        // 1. 全选和取消全选做法：  让下面所有复选框的checked属性（选中状态） 跟随 全选按钮即可
        // 获取元素
        var j_cbAll = document.getElementById('j_cbAll'); // 全选按钮
        var j_tbs = document.getElementById('j_tb').getElementsByTagName('input'); // 下面所有的复选框
        // 注册事件
        j_cbAll.onclick = function() {
                // this.checked 它可以得到当前复选框的选中状态如果是true 就是选中，如果是false 就是未选中
                console.log(this.checked);
                for (var i = 0; i < j_tbs.length; i++) {
                    j_tbs[i].checked = this.checked;
                }
            }
            // 2. 下面复选框需要全部选中， 上面全选才能选中做法： 给下面所有复选框绑定点击事件，每次点击，都要循环查看下面所有的复选框是否有没选中的，如果有一个没选中的， 上面全选就不选中。
        for (var i = 0; i < j_tbs.length; i++) {
            j_tbs[i].onclick = function() {
                // flag 控制全选按钮是否选中
                var flag = true;
                // 每次点击下面的复选框都要循环检查者4个小按钮是否全被选中
                for (var i = 0; i < j_tbs.length; i++) {
                    if (!j_tbs[i].checked) {
                        flag = false;
                        break; // 退出for循环 这样可以提高执行效率 因为只要有一个没有选中，剩下的就无需循环判断了
                    }
                }
                j_cbAll.checked = flag;
            }
        }
    </script>
</body>
```

## 5 自定义属性操作

### 5.1 属性操作

```html
<body>
    <div id="demo" index="1" class="nav"></div>
    <script>
        var div = document.querySelector('div');
        // 1. 获取元素属性
        // (1) element.属性
        console.log(div.id);
        //(2) element.getAttribute('属性')  get得到获取 attribute 属性的意思 我们程序员自己添加的属性我们称为自定义属性 index
        console.log(div.getAttribute('id'));
        console.log(div.getAttribute('index'));
        // 2. 设置元素属性值
        // (1) element.属性= '值'
        div.id = 'text';
        div.index = '2';
        div.className = 'na';
        // (2) element.setAttribute('属性', '值');  主要针对于自定义属性
        div.setAttribute('id', 'set');
        div.setAttribute('class', 'naves'); // class 特殊  这里面写的就是class 不是className
        // 3 移除属性 removeAttribute(属性)    
        div.removeAttribute('index');
        div.removeAttribute('id');
    </script>
</body>
```

### 5.2 tab栏切换

```html
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        li {
            list-style-type: none;
        }
        
        .tab {
            width: 978px;
            margin: 100px auto;
        }
        
        .tab_list {
            height: 39px;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
        }
        
        .tab_list li {
            float: left;
            height: 39px;
            line-height: 39px;
            padding: 0 20px;
            text-align: center;
            cursor: pointer;
        }
        
        .tab_list .current {
            background-color: #c81623;
            color: #fff;
        }
        
        .item_info {
            padding: 20px 0 0 20px;
        }
        
        .item {
            display: none;
        }
    </style>
</head>

<body>
    <div class="tab">
        <div class="tab_list">
            <ul>
                <li class="current">商品介绍</li>
                <li>规格与包装</li>
                <li>售后保障</li>
                <li>商品评价（50000）</li>
                <li>手机社区</li>
            </ul>
        </div>
        <div class="tab_con">
            <div class="item" style="display: block;">
                商品介绍模块内容
            </div>
            <div class="item">
                规格与包装模块内容
            </div>
            <div class="item">
                售后保障模块内容
            </div>
            <div class="item">
                商品评价（50000）模块内容
            </div>
            <div class="item">
                手机社区模块内容
            </div>

        </div>
    </div>
    <script>
        // 获取元素
        var tab_list = document.querySelector('.tab_list');
        var lis = tab_list.querySelectorAll('li');
        var items = document.querySelectorAll('.item');
        // for循环绑定点击事件
        for (var i = 0; i < lis.length; i++) {
            // 开始给5个小li 设置索引号 
            lis[i].setAttribute('index', i);
            lis[i].onclick = function() {
                // 1. 上的模块选项卡，点击某一个，当前这一个底色会是红色，其余不变（排他思想） 修改类名的方式

                // 干掉所有人 其余的li清除 class 这个类
                for (var i = 0; i < lis.length; i++) {
                    lis[i].className = '';
                }
                // 留下我自己 
                this.className = 'current';
                // 2. 下面的显示内容模块
                var index = this.getAttribute('index');
                console.log(index);
                // 干掉所有人 让其余的item 这些div 隐藏
                for (var i = 0; i < items.length; i++) {
                    items[i].style.display = 'none';
                }
                // 留下我自己 让对应的item 显示出来
                items[index].style.display = 'block';
            }
        }
    </script>
</body>
```

### 5.3 自定义属性

```html
<div getTime="20" data-index="2" data-list-name="andy"></div>
    <script>
        var div = document.querySelector('div');
        // console.log(div.getTime);
        console.log(div.getAttribute('getTime'));
        div.setAttribute('data-time', 20);
        console.log(div.getAttribute('data-index'));
        console.log(div.getAttribute('data-list-name'));

        // h5新增的获取自定义属性的方法 它只能获取data-开头的
        // dataset 是一个集合里面存放了所有以data开头的自定义属性
        console.log(div.dataset);
        console.log(div.dataset.index);
        console.log(div.dataset['index']);

        // 如果自定义属性里面有多个-链接的单词，我们获取的时候采取 驼峰命名法
        console.log(div.dataset.listName);
        console.log(div.dataset['listName']);
    </script>
```

## 6 节点

网页中的所有内容都是节点（标签、属性、文本、注释等），在DOM 中，节点使用 node 来表示。

​	HTML DOM 树中的所有节点均可通过 JavaScript 进行访问，所有 HTML 元素（节点）均可被修改，也可以创建或删除

​	一般地，节点至少拥有nodeType（节点类型）、nodeName（节点名称）和nodeValue（节点值）这三个基本属性。

![1550970986988](images/节点类型.png)

### 6.1 父节点

```html
<body>
    <!-- 节点的优点 -->
    <div>我是div</div>
    <span>我是span</span>
    <ul>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
    </ul>
    <div class="demo">
        <div class="box">
            <span class="erweima">×</span>
        </div>
    </div>

    <script>
        // 1. 父节点 parentNode
        var erweima = document.querySelector('.erweima');
        // var box = document.querySelector('.box');
        // 得到的是离元素最近的父级节点(亲爸爸) 如果找不到父节点就返回为 null
        console.log(erweima.parentNode);
    </script>
</body>
```

### 6.2 子元素节点

```html
<body>
    <!-- 节点的优点 -->
    <div>我是div</div>
    <span>我是span</span>
    <ul>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>

    </ul>
    <ol>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
    </ol>

    <div class="demo">
        <div class="box">
            <span class="erweima">×</span>
        </div>
    </div>

    <script>
        // DOM 提供的方法（API）获取
        var ul = document.querySelector('ul');
        var lis = ul.querySelectorAll('li');
        // 1. 子节点  childNodes 所有的子节点 包含 元素节点 文本节点等等
        console.log(ul.childNodes);
        console.log(ul.childNodes[0].nodeType); // 文本为3
        console.log(ul.childNodes[1].nodeType); // 元素节点
        // 2. children 获取所有的子元素节点 也是我们实际开发常用的
        console.log(ul.children);
      
    </script>
```

### 6.3 第一个元素和最后一个节点

```html
<body>
    <ol>
        <li>我是li1</li>
        <li>我是li2</li>
        <li>我是li3</li>
        <li>我是li4</li>
        <li>我是li5</li>
    </ol>
    <script>
        var ol = document.querySelector('ol');
        // 1. firstChild 第一个子节点 不管是文本节点还是元素节点
        console.log(ol.firstChild);
        console.log(ol.lastChild);
        // 2. firstElementChild 返回第一个子元素节点 ie9才支持
        console.log(ol.firstElementChild);
        console.log(ol.lastElementChild);
        // 3. 实际开发的写法  既没有兼容性问题又返回第一个子元素
        console.log(ol.children[0]);
        console.log(ol.children[ol.children.length - 1]);
    </script>
</body>
```

### 6.4 新浪下拉菜单

```html
<style>
        * {
            margin: 0;
            padding: 0;
        }
        
        li {
            list-style-type: none;
        }
        
        a {
            text-decoration: none;
            font-size: 14px;
        }
        
        .nav {
            margin: 100px;
        }
        
        .nav>li {
            position: relative;
            float: left;
            width: 80px;
            height: 41px;
            text-align: center;
        }
        
        .nav li a {
            display: block;
            width: 100%;
            height: 100%;
            line-height: 41px;
            color: #333;
        }
        
        .nav>li>a:hover {
            background-color: #eee;
        }
        
        .nav ul {
            display: none;
            position: absolute;
            top: 41px;
            left: 0;
            width: 100%;
            border-left: 1px solid #FECC5B;
            border-right: 1px solid #FECC5B;
        }
        
        .nav ul li {
            border-bottom: 1px solid #FECC5B;
        }
        
        .nav ul li a:hover {
            background-color: #FFF5DA;
        }
    </style>
</head>

<body>
    <ul class="nav">
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
    </ul>
    <script>
        // 1. 获取元素
        var nav = document.querySelector('.nav');
        var lis = nav.children; // 得到4个小li
        // 2.循环注册事件
        for (var i = 0; i < lis.length; i++) {
            lis[i].onmouseover = function() {
                this.children[1].style.display = 'block';
            }
            lis[i].onmouseout = function() {
                this.children[1].style.display = 'none';
            }
        }
    </script>
</body>

```

### 6.5 创建和添加元素

```html
ul>
        <li>123</li>
    </ul>
    <script>
        // 1 创建节点元素
        var li = document.createElement('li');
        // 2. 添加节点 node.appendChild(child)  node 父级  child 是子级 后面追加元素  类似于数组中的push
        var ul = document.querySelector('ul');
        ul.appendChild(li);
        // 3. 添加节点 node.insertBefore(child, 指定元素);
        var lis = document.createElement('li');
        ul.insertBefore(lili, ul.children[0]);
        // 4. 我们想要页面添加一个新的元素 ： 1. 创建元素 2. 添加元素
    </script>
```

### 6.6 发布留言

```html
 <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        body {
            padding: 100px;
        }
        
        textarea {
            width: 200px;
            height: 100px;
            border: 1px solid pink;
            outline: none;
            resize: none;
        }
        
        ul {
            margin-top: 50px;
        }
        
        li {
            width: 300px;
            padding: 5px;
            background-color: rgb(245, 209, 243);
            color: red;
            font-size: 14px;
            margin: 15px 0;
        }
    </style>
</head>

<body>
    <textarea name="" id=""></textarea>
    <button>发布</button>
    <ul>

    </ul>
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value;
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
            }
        }
    </script>
</body>

```

### 6.7 删除节点

```html
<body>
    <button>删除</button>
    <ul>
        <li>熊大</li>
        <li>熊二</li>
        <li>光头强</li>
    </ul>
    <script>
        // 1.获取元素
        var ul = document.querySelector('ul');
        var btn = document.querySelector('button');
        // 2. 删除元素  node.removeChild(child)
        // ul.removeChild(ul.children[0]);
        // 3. 点击按钮依次删除里面的孩子
        btn.onclick = function() {
            if (ul.children.length == 0) {
                this.disabled = true;
            } else {
                ul.removeChild(ul.children[0]);
            }
        }
    </script>
</body>
```

### 6.8 删除留言案例

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        body {
            padding: 100px;
        }
        
        textarea {
            width: 200px;
            height: 100px;
            border: 1px solid pink;
            outline: none;
            resize: none;
        }
        
        ul {
            margin-top: 50px;
        }
        
        li {
            width: 300px;
            padding: 5px;
            background-color: rgb(245, 209, 243);
            color: red;
            font-size: 14px;
            margin: 15px 0;
        }
        
        li a {
            float: right;
        }
    </style>
</head>

<body>
    <textarea name="" id=""></textarea>
    <button>发布</button>
    <ul>

    </ul>
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value + "<a href='javascript:;'>删除</a>";
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
                // (3) 删除元素 删除的是当前链接的li  它的父亲
                var as = document.querySelectorAll('a');
                for (var i = 0; i < as.length; i++) {
                    as[i].onclick = function() {
                        // node.removeChild(child); 删除的是 li 当前a所在的li  this.parentNode;
                        ul.removeChild(this.parentNode);
                    }
                }
            }
        }
    </script>
</body>
```

### 6.9 克隆拷贝

```html
<body>
    <ul>
        <li>1111</li>
        <li>2</li>
        <li>3</li>
    </ul>
    <script>
        var ul = document.querySelector('ul');
        // 1. node.cloneNode(); 括号为空或者里面是false 浅拷贝 只复制标签不复制里面的内容
        // 2. node.cloneNode(true); 括号为true 深拷贝 复制标签复制里面的内容
        var lili = ul.children[0].cloneNode(true);
        ul.appendChild(lili);
    </script>
```

# 三 Web APIs第三天

## 1 动态生成表格

```html
<style>
        table {
            width: 500px;
            margin: 100px auto;
            border-collapse: collapse;
            text-align: center;
        }
        
        td,
        th {
            border: 1px solid #333;
        }
        
        thead tr {
            height: 40px;
            background-color: #ccc;
        }
    </style>
</head>

<body>
    <table cellspacing="0">
        <thead>
            <tr>
                <th>姓名</th>
                <th>科目</th>
                <th>成绩</th>
                <th>操作</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>
    <script>
        // 1.先去准备好学生的数据
        var datas = [{
            name: '魏璎珞',
            subject: 'JavaScript',
            score: 100
        }, {
            name: '弘历',
            subject: 'JavaScript',
            score: 98
        }, {
            name: '傅恒',
            subject: 'JavaScript',
            score: 99
        }, {
            name: '明玉',
            subject: 'JavaScript',
            score: 88
        }, {
            name: '大猪蹄子',
            subject: 'JavaScript',
            score: 0
        }];
        // 2. 往tbody 里面创建行： 有几个人（通过数组的长度）我们就创建几行
        var tbody = document.querySelector('tbody');
        var str = ''
        for (var i = 0; i < datas.length; i++) {
            var obj = datas[i]
            str += `<tr>
                <td>${obj.name}</td>
                <td>${obj.subject}</td>
                <td>${obj.score}</td>
                <td><a href="">删除</a></td>
            </tr>`
        }
        console.log(str)
        tbody.innerHTML = str
    </script>
</body>
```

## 2 注册事件的两种方式

```html
<button>传统注册事件</button>
    <button>方法监听注册事件</button>
    <button>ie9 attachEvent</button>
    <script>
        // 1、传统的方式
        var btn = document.querySelectorAll('button');
        btn[0].onclick = function() {
            alert('22')
        }
        btn[0].onclick = function() {
                alert('33')
            }
            //重复值会覆盖上面的操作
            // 2. 事件侦听注册事件 addEventListener 
            // (1) 里面的事件类型是字符串 必定加引号 而且不带on
            // (2) 同一个元素 同一个事件可以添加多个侦听器（事件处理程序）
        btn[1].addEventListener('click', function() {
            alert('44')
        })
        btn[1].addEventListener('click', function() {
                alert('55')
            })
            // 不会覆盖原来的值，会追加
            // 3. attachEvent ie9以前的版本支持
        btn[2].attachEvent('click', function() {
            alert('66')
        })
    </script>
```

## 3 删除事件

```html
<style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <script>
        var divs = document.querySelectorAll('div');
        divs[0].onclick = function() {
                alert(11);
                // 1. 传统方式删除事件
                divs[0].onclick = null;
            }
            // 2. removeEventListener 删除事件
        divs[1].addEventListener('click', fn) // 里面的fn 不需要调用加小括号

        function fn() {
            alert(22);
            divs[1].removeEventListener('click', fn);
        }
        // 3. detachEvent
        divs[2].attachEvent('onclick', fn1);

        function fn1() {
            alert(33);
            divs[2].detachEvent('onclick', fn1);
        }
    </script>
</body>
```

### 3.1 动态生成表格

```html
<style>
        table {
            width: 500px;
            margin: 100px auto;
            border-collapse: collapse;
            text-align: center;
        }
        
        td,
        th {
            border: 1px solid #333;
        }
        
        thead tr {
            height: 40px;
            background-color: #ccc;
        }
    </style>
</head>

<body>
    <table cellspacing="0">
        <thead>
            <tr>
                <th>姓名</th>
                <th>科目</th>
                <th>成绩</th>
                <th>操作</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>
    <script>
        // 1.先去准备好学生的数据
        var datas = [{
            name: '魏璎珞',
            subject: 'JavaScript',
            score: 100
        }, {
            name: '弘历',
            subject: 'JavaScript',
            score: 98
        }, {
            name: '傅恒',
            subject: 'JavaScript',
            score: 99
        }, {
            name: '明玉',
            subject: 'JavaScript',
            score: 88
        }, {
            name: '大猪蹄子',
            subject: 'JavaScript',
            score: 0
        }];
        // 2. 往tbody 里面创建行： 有几个人（通过数组的长度）我们就创建几行
        var tbody = document.querySelector('tbody');
        var str = ''
        for (var i = 0; i < datas.length; i++) {
            var obj = datas[i]
            str += `<tr>
                <td>${obj.name}</td>
                <td>${obj.subject}</td>
                <td>${obj.score}</td>
                <td><a href="">删除</a></td>
            </tr>`
        }
        console.log(str)
        tbody.innerHTML = str
            // 3. 删除操作 开始 
        var as = document.querySelectorAll('a');
        var trs = document.querySelectorAll('tbody tr');
        for (var i = 0; i < as.length; i++) {
            as[i].onclick = function(e) {
                // 点击a 删除 当前a 所在的行(链接的爸爸的爸爸)  node.removeChild(child) 
                e.preventDefault(); // a是链接，会跳转，此处设置阻止默认跳转样式  或者把a标签换成其他标签
                tbody.removeChild(this.parentNode.parentNode);

            }
        }
    </script>
</body>
```



## 4 DOM事件流

```html
 <div class="father">
        <div class="son">son盒子</div>
    </div>
    <script>
        // dom 事件流 三个阶段
        // 1. JS 代码中只能执行捕获或者冒泡其中的一个阶段。
        // 2. onclick 和 attachEvent（ie） 只能得到冒泡阶段。
        // 3. 捕获阶段 如果addEventListener 第三个参数是 true 那么则处于捕获阶段  document -> html -> body -> father -> son
        var son = document.querySelector('.son');
        son.addEventListener('click', function() {
            alert('son');
        }, true);
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, true);
        // 4. 冒泡阶段 如果addEventListener 第三个参数是 false 或者 省略 那么则处于冒泡阶段  son -> father ->body -> html -> document
        var son = document.querySelector('.son');
        son.addEventListener('click', function() {
            alert('son');
        }, false);
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, false);
        document.addEventListener('click', function() {
            alert('document');
        })
    </script>
```

## 5 事件对象

```html
<style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
  </style>
</head>

<body>
    <div>123</div>
    <script>
        // 事件对象
        var div = document.querySelector('div');
        div.onclick = function(e) {
                // console.log(e);
                // console.log(window.event);
                // e = e || window.event;
                console.log(e);


            }
            // div.addEventListener('click', function(e) {
            //         console.log(e);

        //     })
        // 1. event 就是一个事件对象 写到我们侦听函数的 小括号里面 当形参来看
        // 2. 事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数
        // 3. 事件对象 是 我们事件的一系列相关数据的集合 跟事件相关的 比如鼠标点击里面就包含了鼠标的相关信息，鼠标坐标啊，如果是键盘事件里面就包含的键盘事件的信息 比如 判断用户按下了那个键
        // 4. 这个事件对象我们可以自己命名 比如 event 、 evt、 e
        // 5. 事件对象也有兼容性问题 ie678 通过 window.event 兼容性的写法  e = e || window.event;
    </script>
```

## 6 e.target和this

```html
 <style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <div>123</div>
    <ul>
        <li>abc</li>
        <li>abc</li>
        <li>abc</li>
    </ul>
    <script>
        // 常见事件对象的属性和方法
        // 1. e.target 返回的是触发事件的对象（元素）  this 返回的是绑定事件的对象（元素）
        // 区别 ： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁
        var div = document.querySelector('div');
        div.addEventListener('click', function(e) {
            console.log(e.target);
            console.log(this);

        })
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
                // 我们给ul 绑定了事件  那么this 就指向ul  
                console.log(this);
                console.log(e.currentTarget);

                // e.target 指向我们点击的那个对象 谁触发了这个事件 我们点击的是li e.target 指向的就是li
                console.log(e.target);

            })
            // 了解兼容性
            // div.onclick = function(e) {
            //     e = e || window.event;
            //     var target = e.target || e.srcElement;
            //     console.log(target);

        // }
        // 2. 了解 跟 this 有个非常相似的属性 currentTarget  ie678不认识
    </script>
</body>
```

## 7 事件对象阻止默认行为

```html
<body>
    <div>123</div>
    <a href="http://www.baidu.com">百度</a>
    <form action="http://www.baidu.com">
        <input type="submit" value="提交" name="sub">
    </form>
    <script>
        // 常见事件对象的属性和方法
        // 1. 返回事件类型
        var div = document.querySelector('div');
        div.addEventListener('click', fn);
        div.addEventListener('mouseover', fn);
        div.addEventListener('mouseout', fn);

        function fn(e) {
            console.log(e.type);

        }
        // 2. 阻止默认行为（事件） 让链接不跳转 或者让提交按钮不提交
        var a = document.querySelector('a');
        // a.addEventListener('click', function(e) {
        //     e.preventDefault(); //  dom 标准写法
        // })
        a.addEventListener('click', function(e) {
            e.preventDefault();
        })

        // 3. 传统的注册方式
        a.onclick = function(e) {
            // 普通浏览器 e.preventDefault();  方法
            // e.preventDefault();
            // 低版本浏览器 ie678  returnValue  属性
            // e.returnValue;
            // 我们可以利用return false 也能阻止默认行为 没有兼容性问题 特点： return 后面的代码不执行了， 而且只限于传统的注册方式
            return false;
            alert(11);
        }
    </script>
</body>
```

## 8 阻止冒泡事件

```html
 <style>
        .father {
            overflow: hidden;
            width: 300px;
            height: 300px;
            margin: 100px auto;
            background-color: pink;
            text-align: center;
        }
        
        .son {
            width: 200px;
            height: 200px;
            margin: 50px;
            background-color: purple;
            line-height: 200px;
            color: #fff;
        }
    </style>
</head>

<body>
    <div class="father">
        <div class="son">son儿子</div>
    </div>
    <script>
        // 常见事件对象的属性和方法
        // 阻止冒泡  dom 推荐的标准 stopPropagation() 
        var son = document.querySelector('.son');
        son.addEventListener('click', function(e) {
            alert('son');
            e.stopPropagation() // stop 停止  Propagation 传播
            e.cancelBubble = true; // 非标准 cancel 取消 bubble 泡泡
        }, false);

        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, false);
        document.addEventListener('click', function() {
            alert('document');
        })
    </script>
</body>
```

## 9 事件委托

```html
<body>
    <ul>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
    </ul>
    <script>
        // 事件委托的核心原理：给父节点添加侦听器， 利用事件冒泡影响每一个子节点
        var ul = document.querySelector('ul');
        // 1、方法一 排他思想 点击显示粉色
         ul.addEventListener('click', function(e) {
        // 排他思想
       for (var i = 0; i < ul.children.length; i++) {
         ul.children[i].style.backgroundColor = '';
         }
           // alert('知否，点我的');
          // e.target 这个可以得到我们点击的对象
            e.target.style.backgroundColor = 'pink';
         })

        // 2、点击显示粉色

        ul.addEventListener('click', function(e) {
            var index;
            for (var i = 0; i < ul.children.length; i++) {
                ul.children[i].style.backgroundColor = '';
                if (e.target === ul.children[i]) {
                    index = i;
                }
            }
            e.target.style.backgroundColor = 'pink';
        })
    </script>
</body>
```

## 10 鼠标事件

```html
<style>
        body {
            height: 3000px;
        }
    </style>
</head>

<body>
    <script>
        // 鼠标事件对象 MouseEvent
        document.addEventListener('click', function(e) {
            // 1. client 鼠标在可视区的x和y坐标
            console.log(e.clientX);
            console.log(e.clientY);
            console.log('---------------------');

            // 2. page 鼠标在页面文档的x和y坐标
            console.log(e.pageX);
            console.log(e.pageY);
            console.log('---------------------');

            // 3. screen 鼠标在电脑屏幕的x和y坐标
            console.log(e.screenX);
            console.log(e.screenY);

        })
    </script>
</body>

```

### 10.1 天使跟随鼠标移动

```html
<style>
        img {
            position: absolute;
            top: 2px;
        }
    </style>
</head>

<body>
    <img src="images/angel.gif" alt="">
    <script>
        var pic = document.querySelector('img');
        document.addEventListener('mousemove', function(e) {
            // 1. mousemove只要我们鼠标移动1px 就会触发这个事件
            // console.log(1);
            // 2.核心原理： 每次鼠标移动，我们都会获得最新的鼠标坐标， 把这个x和y坐标做为图片的top和left 值就可以移动图片
            var x = e.pageX;
            var y = e.pageY;
            console.log('x坐标是' + x, 'y坐标是' + y);
            //3 . 千万不要忘记给left 和top 添加px 单位
            pic.style.left = x - 50 + 'px';
            pic.style.top = y - 40 + 'px';


        });
    </script>
```

# 四 Web APIs第四天

## 1 键盘事件

### 1.1 键盘常用事件

```html
<script>
        // 常用的键盘事件
        //1. keyup 按键弹起的时候触发 
        // document.onkeyup = function() {
        //         console.log('我弹起了');

        //     }
        document.addEventListener('keyup', function() {
            console.log('我弹起了');
        })

        //3. keypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keypress', function() {
                console.log('我按下了press');
            })
            //2. keydown 按键按下的时候触发  能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keydown', function() {
                console.log('我按下了down');
            })
            // 4. 三个事件的执行顺序  keydown -- keypress -- keyup
    </script>
```

### 1.2  -键盘事件对象之keyCode属性

```html
<script>
        // 键盘事件对象中的keyCode属性可以得到相应键的ASCII码值
        // 1. 我们的keyup 和keydown事件不区分字母大小写  a 和 A 得到的都是65
        // 2. 我们的keypress 事件 区分字母大小写  a  97 和 A 得到的是65
        document.addEventListener('keyup', function(e) {
            // console.log(e);
            console.log('up:' + e.keyCode);
            // 我们可以利用keycode返回的ASCII码值来判断用户按下了那个键
            if (e.keyCode === 65) {
                alert('您按下的a键');
            } else {
                alert('您没有按下a键')
            }

        })
        document.addEventListener('keypress', function(e) {
            // console.log(e);
            console.log('press:' + e.keyCode);

        })
    </script>
```

### 1.3 京东按键案例

```js
 <input type="text">
    <script>
        // 核心思路： 检测用户是否按下了s 键，如果按下s 键，就把光标定位到搜索框里面
        // 使用键盘事件对象里面的keyCode 判断用户按下的是否是s键
        // 搜索框获得焦点： 使用 js 里面的 focus() 方法
        var search = document.querySelector('input');
        document.addEventListener('keyup', function(e) {
            // console.log(e.keyCode);
            if (e.keyCode === 83) {
                search.focus();
            }
        })
    </script>
```

### 1.4 京东快递单号查询

```html
<style>
        * {
            margin: 0;
            padding: 0;
        }
        
        .search {
            position: relative;
            width: 178px;
            margin: 100px;
        }
        
        .con {
            display: none;
            position: absolute;
            top: -40px;
            width: 171px;
            border: 1px solid rgba(0, 0, 0, .2);
            box-shadow: 0 2px 4px rgba(0, 0, 0, .2);
            padding: 5px 0;
            font-size: 18px;
            line-height: 20px;
            color: #333;
        }
        
        .con::before {
            content: '';
            width: 0;
            height: 0;
            position: absolute;
            top: 28px;
            left: 18px;
            border: 8px solid #000;
            border-style: solid dashed dashed;
            border-color: #fff transparent transparent;
        }
    </style>
</head>

<body>
    <div class="search">
        <div class="con">123</div>
        <input type="text" placeholder="请输入您的快递单号" class="jd">
    </div>
    <script>
        // 快递单号输入内容时， 上面的大号字体盒子（con）显示(这里面的字号更大）
        // 表单检测用户输入： 给表单添加键盘事件
        // 同时把快递单号里面的值（value）获取过来赋值给 con盒子（innerText）做为内容
        // 如果快递单号里面内容为空，则隐藏大号字体盒子(con)盒子
        var con = document.querySelector('.con');
        var jd_input = document.querySelector('.jd');
        jd_input.addEventListener('keyup', function() {
                // console.log('输入内容啦');
                if (this.value == '') {
                    con.style.display = 'none';
                } else {
                    con.style.display = 'block';
                    con.innerText = this.value;
                }
            })
            // 当我们失去焦点，就隐藏这个con盒子
        jd_input.addEventListener('blur', function() {
                con.style.display = 'none';
            })
            // 当我们获得焦点，就显示这个con盒子
        jd_input.addEventListener('focus', function() {
            if (this.value !== '') {
                con.style.display = 'block';
            }
        })
    </script>
</body>
```

## 2 BOM

### 2.1window 对象的常见事件

```js
// window.onload = function() {
        //     var btn = document.querySelector('button');
        //     btn.addEventListener('click', function() {
        //         alert('点击我');
        //     })
        // }
        // window.onload = function() {
        //     alert(22);
        // }
        window.addEventListener('load', function() {
            var btn = document.querySelector('button');
            btn.addEventListener('click', function() {
                alert('点击我');
            })
        })
        window.addEventListener('load', function() {

            alert(22);
        })
        document.addEventListener('DOMContentLoaded', function() {
            alert(33);
        })

        // load 等页面内容全部加载完毕，包含页面dom元素 图片 flash  css 等等
        // DOMContentLoaded 是DOM 加载完毕，不包含图片 falsh css 等就可以执行 加载速度比 load更快一些
```

### 2.2 调整窗口大小

```html
<style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <script>
        window.addEventListener('load', function() {
            var div = document.querySelector('div');
            window.addEventListener('resize', function() {
                console.log(window.log('变化了');
                if (window.innerWidth <= 800) {
                    div.style.display = 'none';
                } else {
                    div.style.display = 'block';
                }

            })
        })
    </script>
    <div></div>
```

## 3 定时器

### 3.1 开启定时器--setTimeout

```html
<script>
        // 1. setTimeout 
        // 语法规范：  window.setTimeout(调用函数, 延时时间);
        // 1. 这个window在调用的时候可以省略
        // 2. 这个延时时间单位是毫秒 但是可以省略，如果省略默认的是0
        // 3. 这个调用函数可以直接写函数 还可以写 函数名 还有一个写法 '函数名()'
        // 4. 页面中可能有很多的定时器，我们经常给定时器加标识符 （名字)
        // setTimeout(function() {
        //         alert('时间到了')
        //     }, 3000)
        function callback() {
            console.log('爆炸吧');
            console.log(this); //this在定时器中指向window

        }
        var timer1 = setTimeout(callback, 1000);
        var timer2 = setTimeout(callback, 3000);
        var timer3 = setTimeout(callback, 4000);
        var timer4 = setTimeout(callback, 000);
        // setTimeout('callback()', 3000); // 我们不提倡这个写法
    </script>
```

### 3.2 取消定时器

```html
<body>
    <button>点击停止定时器</button>
    <script>
        var btn = document.querySelector('button');
        var timer = setTimeout(function() {
            console.log('爆炸了');

        }, 5000)
        btn.addEventListener('click', function() {
            clearTimeout(timer);
        })
    </script>

</body>
```

### 3.3 定时器--setInterval

```js

        // 1. setInterval 
        // 语法规范：  window.setInterval(调用函数, 延时时间);
        setInterval(function() {
            console.log('继续输出');

        }, 1000);
        // 2. setTimeout  延时时间到了，就去调用这个回调函数，只调用一次 就结束了这个定时器
        // 3. setInterval  每隔这个延时时间，就去调用这个回调函数，会调用很多次，重复调用这个函数
  
```

### 3.4 清除定时器

```html
<body>
    <button class="begin">开启定时器</button>
    <button class="stop">停止定时器</button>
    <script>
        var begin = document.querySelector('.begin');
        var stop = document.querySelector('.stop');
        var timer = null; // 全局变量  null是一个空对象
        begin.addEventListener('click', function() {
            timer = setInterval(function() {
                console.log('ni hao ma');

            }, 1000);
        })
        stop.addEventListener('click', function() {
            clearInterval(timer);
        })
    </script>
</body>
```

### 3.5 倒计时案例

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            margin: 200px;
        }
        
        span {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: #333;
            font-size: 20px;
            color: #fff;
            text-align: center;
            line-height: 40px;
        }
    </style>
</head>

<body>
    <div>
        <span class="hour">1</span>
        <span class="minute">2</span>
        <span class="second">3</span>
    </div>
    <script>
        // 1. 获取元素 
        var hour = document.querySelector('.hour'); // 小时的黑色盒子
        var minute = document.querySelector('.minute'); // 分钟的黑色盒子
        var second = document.querySelector('.second'); // 秒数的黑色盒子
        var inputTime = +new Date('2019-5-1 18:00:00'); // 返回的是用户输入时间总的毫秒数
        countDown(); // 我们先调用一次这个函数，防止第一次刷新页面有空白 
        // 2. 开启定时器
        setInterval(countDown, 1000);

        function countDown() {
            var nowTime = +new Date(); // 返回的是当前时间总的毫秒数
            var times = (inputTime - nowTime) / 1000; // times是剩余时间总的秒数 
            var h = parseInt(times / 60 / 60 % 24); //时
            h = h < 10 ? '0' + h : h;
            hour.innerHTML = h; // 把剩余的小时给 小时黑色盒子
            var m = parseInt(times / 60 % 60); // 分
            m = m < 10 ? '0' + m : m;
            minute.innerHTML = m;
            var s = parseInt(times % 60); // 当前的秒
            s = s < 10 ? '0' + s : s;
            second.innerHTML = s;
        }
    </script>
</body>
```

### 3.6 发送短信anli

```html
<body>
    手机号码： <input type="number"> <button>发送</button>
    <script>
        // 按钮点击之后，会禁用 disabled 为true 
        // 同时按钮里面的内容会变化， 注意 button 里面的内容通过 innerHTML修改
        // 里面秒数是有变化的，因此需要用到定时器
        // 定义一个变量，在定时器里面，不断递减
        // 如果变量为0 说明到了时间，我们需要停止定时器，并且复原按钮初始状态
        var btn = document.querySelector('button');
        var time = 3; // 定义剩下的秒数
        btn.addEventListener('click', function() {
            btn.disabled = true;
            var timer = setInterval(function() {
                if (time == 0) {
                    // 清除定时器和复原按钮
                    clearInterval(timer);
                    btn.disabled = false;
                    btn.innerHTML = '发送';
                } else {
                    btn.innerHTML = '还剩下' + time + '秒';
                    time--;
                }
            }, 1000);

        })
    </script>
</body>

```

## 4 this指向问

```html
this指向
        // 1. 普通函数中this指向的window
        // 2. 对象中中的this指向的是当前这个对象
        // 3. 事件中this指向的是事件源
        // 4. 构造函数中的this指向的是new出来的那个实例对象
        // 5. 定时器中this指向的是window
        // 备注 this始终指向的是函数的调用者
        
        <body>
    <button>点击</button>
    <script>
        // this 指向问题 一般情况下this的最终指向的是那个调用它的对象

        // 1. 全局作用域或者普通函数中this指向全局对象window（ 注意定时器里面的this指向window）
        console.log(this);

        function fn() {
            console.log(this);

        }
        window.fn();
        window.setTimeout(function() {
            console.log(this);

        }, 1000);
        // 2. 方法调用中谁调用this指向谁
        var o = {
            sayHi: function() {
                console.log(this); // this指向的是 o 这个对象

            }
        }
        o.sayHi();
        var btn = document.querySelector('button');
        // btn.onclick = function() {
        //     console.log(this); // this指向的是btn这个按钮对象

        // }
        btn.addEventListener('click', function() {
                console.log(this); // this指向的是btn这个按钮对象

            })
            // 3. 构造函数中this指向构造函数的实例
        function Fun() {
            console.log(this); // this 指向的是fun 实例对象

        }
        var fun = new Fun();
    </script>
</body>

```

## 5 location

![1551322416716](images/location.png)

### 5.1 5s后跳转页面

```html
<button>点击</button>
    <div></div>
    <script>
        var btn = document.querySelector('button');
        var div = document.querySelector('div');
        btn.addEventListener('click', function() {
            // console.log(location.href);
            location.href = 'http://www.itcast.cn';
        })
        var timer = 5;
        setInterval(function() {
            if (timer == 0) {
                location.href = 'http://www.itcast.cn';
            } else {
                div.innerHTML = '您将在' + timer + '秒钟之后跳转到首页';
                timer--;
            }

        }, 1000);
    </script>
```

### 5.2 获取URL参数

```js
var url = 'https://www.itcast.com/index.html?username=daxiong&age=10';
        var search = url.split('?')
        var search1 = search[1]
        var search2 = search[1].split('&')
        var obj = {};
        for (var i = 0; i < search2.length; i++) {
            var search3 = search2[i];
            var search4 = search3.split('=');
            var key = search4[0];
            var tem = search4[1];
            obj[key] = tem;
        }
        console.log(obj, 555);

        // es6提供
        var param = new URLSearchParams('?username=daxiong&age=10');
        console.log(param.get('username')); // 此处获得的值是daxiong,只写get('username')，得不到对应值daxiong；这是因为，URLSearchParams get() 方法返回url查询字符串中第一个与key匹配的value；第一个与key匹配的value应该是https://www.itcast.com/index.html?username；或者直接截取？后面的参数部分
        console.log(param.get('age'));

        // var url = "http://www.softwhy.com/forum.php?mod=viewthread&tid=4596";
        // var urlSearchParam = new URLSearchParams(url.split("?")[1]);
        // console.log(urlSearchParam.get("mod"));

        // 获取key为"mod"的对应value值，如果有重复的key，那么只会获取第一个对应的value。
```

## 6 location navigator history

```js
    // * location navigator history
        //  location.href 1. 获取url地址 2. 跳转 3. 刷新
        // location.search 获取url参数 ?name=klxin&age=16
    //  * navigator.userAgent 获取设备信息
        navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i)) {
            window.location.href = "../H5/index.html"; //手机
    //  * history
        // 1. 前进 history.forward()/history.go(1)
        // 2. 后退 history.back()/history.go(-1)
        // 3. 刷新 history.go(0)

        // 所有刷新 1. history.go(0) 2. location.href=location.href 3. location.reload(true)
```

# 五 Web APIs第五天

## 1 offset系列

```html
<div class="father">
        <div class="son"></div>
    </div>
    <div class="w"></div>
    <script>
        // offset 系列
        var father = document.querySelector('.father');
        var son = document.querySelector('.son');
        // 1.可以得到元素的偏移 位置 返回的不带单位的数值  
        console.log(father.offsetTop);
        console.log(father.offsetLeft);
        // 它以带有定位的父亲为准  如果么有父亲或者父亲没有定位 则以 body 为准
        console.log(son.offsetLeft);
        var w = document.querySelector('.w');
        // 2.可以得到元素的大小 宽度和高度 是包含padding + border + width 
        console.log(w.offsetWidth);
        console.log(w.offsetHeight);
        // 3. 返回带有定位的父亲 否则返回的是body
        console.log(son.offsetParent); // 返回带有定位的父亲 否则返回的是body
        console.log(son.parentNode); // 返回父亲 是最近一级的父亲 亲爸爸 不管父亲有没有定位
    </script>
```

### 1.1 offset and style

```html
<style>
        .box {
            width: 200px;
            height: 200px;
            background-color: pink;
            padding: 10px;
        }
    </style>
</head>

<body>
    <div class="box" style="width: 200px;"></div>
    <script>
        // offset与style的区别
        var box = document.querySelector('.box');
        console.log(box.offsetWidth);
        console.log(box.style.width);
        // box.offsetWidth = '300px';
        box.style.width = '300px';
    </script>
</body>
```

## 2 计算鼠标在盒子内的坐标

```html
 <style>
        .login-header {
            width: 100%;
            text-align: center;
            height: 30px;
            font-size: 24px;
            line-height: 30px;
        }
        
        ul,
        li,
        ol,
        dl,
        dt,
        dd,
        div,
        p,
        span,
        h1,
        h2,
        h3,
        h4,
        h5,
        h6,
        a {
            padding: 0px;
            margin: 0px;
        }
        
        .login {
            display: none;
            width: 512px;
            height: 280px;
            position: fixed;
            border: #ebebeb solid 1px;
            left: 50%;
            top: 50%;
            background: #ffffff;
            box-shadow: 0px 0px 20px #ddd;
            z-index: 9999;
            transform: translate(-50%, -50%);
        }
        
        .login-title {
            width: 100%;
            margin: 10px 0px 0px 0px;
            text-align: center;
            line-height: 40px;
            height: 40px;
            font-size: 18px;
            position: relative;
            cursor: move;
        }
        
        .login-input-content {
            margin-top: 20px;
        }
        
        .login-button {
            width: 50%;
            margin: 30px auto 0px auto;
            line-height: 40px;
            font-size: 14px;
            border: #ebebeb 1px solid;
            text-align: center;
        }
        
        .login-bg {
            display: none;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0px;
            left: 0px;
            background: rgba(0, 0, 0, .3);
        }
        
        a {
            text-decoration: none;
            color: #000000;
        }
        
        .login-button a {
            display: block;
        }
        
        .login-input input.list-input {
            float: left;
            line-height: 35px;
            height: 35px;
            width: 350px;
            border: #ebebeb 1px solid;
            text-indent: 5px;
        }
        
        .login-input {
            overflow: hidden;
            margin: 0px 0px 20px 0px;
        }
        
        .login-input label {
            float: left;
            width: 90px;
            padding-right: 10px;
            text-align: right;
            line-height: 35px;
            height: 35px;
            font-size: 14px;
        }
        
        .login-title span {
            position: absolute;
            font-size: 12px;
            right: -20px;
            top: -30px;
            background: #ffffff;
            border: #ebebeb solid 1px;
            width: 40px;
            height: 40px;
            border-radius: 20px;
        }
    </style>
</head>

<body>
    <div class="login-header"><a id="link" href="javascript:;">点击，弹出登录框</a></div>
    <div id="login" class="login">
        <div id="title" class="login-title">登录会员
            <span><a id="closeBtn" href="javascript:void(0);" class="close-login">关闭</a></span>
        </div>
        <div class="login-input-content">
            <div class="login-input">
                <label>用户名：</label>
                <input type="text" placeholder="请输入用户名" name="info[username]" id="username" class="list-input">
            </div>
            <div class="login-input">
                <label>登录密码：</label>
                <input type="password" placeholder="请输入登录密码" name="info[password]" id="password" class="list-input">
            </div>
        </div>
        <div id="loginBtn" class="login-button"><a href="javascript:void(0);" id="login-button-submit">登录会员</a></div>
    </div>
    <!-- 遮盖层 -->
    <div id="bg" class="login-bg"></div>
    <script>
        // 1. 获取元素
        var login = document.querySelector('.login');
        var mask = document.querySelector('.login-bg');
        var link = document.querySelector('#link');
        var closeBtn = document.querySelector('#closeBtn');
        var title = document.querySelector('#title');
        // 2. 点击弹出层这个链接 link  让mask 和login 显示出来
        link.addEventListener('click', function() {
                mask.style.display = 'block';
                login.style.display = 'block';
            })
            // 3. 点击 closeBtn 就隐藏 mask 和 login 
        closeBtn.addEventListener('click', function() {
                mask.style.display = 'none';
                login.style.display = 'none';
            })
            // 4. 开始拖拽
            // (1) 当我们鼠标按下， 就获得鼠标在盒子内的坐标
        title.addEventListener('mousedown', function(e) {
            var x = e.pageX - login.offsetLeft;
            var y = e.pageY - login.offsetTop;
            // (2) 鼠标移动的时候，把鼠标在页面中的坐标，减去 鼠标在盒子内的坐标就是模态框的left和top值
            document.addEventListener('mousemove', move)

            function move(e) {
                login.style.left = e.pageX - x + 'px';
                login.style.top = e.pageY - y + 'px';
            }
            // (3) 鼠标弹起，就让鼠标移动事件移除
            document.addEventListener('mouseup', function() {
                document.removeEventListener('mousemove', move);
            })
        })
    </script>
</body>
```

## 3 client

```html
<style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            border: 10px solid red;
            padding: 10px;
        }
    </style>
</head>

<body>
    <div></div>
    <script>
        // client 宽度 和我们offsetWidth 最大的区别就是 不包含边框
        var div = document.querySelector('div');
        console.log(div.clientWidth);
    </script>
</body>
```

## 4 立即执行函数

```html
<script>
        // 1.立即执行函数: 不需要调用，立马能够自己执行的函数
        function fn() {
            console.log(1);

        }
        fn();
        // 2. 写法 也可以传递参数进来
        // 1.(function() {})()    或者  2. (function(){}());
        (function(a, b) {
            console.log(a + b);
            var num = 10;
        })(1, 2); // 第二个小括号可以看做是调用函数
        (function sum(a, b) {
            console.log(a + b);
            var num = 10; // 局部变量
        }(2, 3));
        // 3. 立即执行函数最大的作用就是 独立创建了一个作用域, 里面所有的变量都是局部变量 不会有命名冲突的情况
    </script>
```

## 5 scroll

```html
 <div>
        我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容 我是内容
    </div>
    <script>
        // scroll 系列
        var div = document.querySelector('div');
        console.log(div.scrollHeight);
        console.log(div.clientHeight);
        // scroll滚动事件当我们滚动条发生变化会触发的事件
        div.addEventListener('scroll', function() {
            console.log(div.scrollTop);

        })
    </script>
```

## 6 仿淘宝固定侧边栏

```html
<style>
        .slider-bar {
            position: absolute;
            left: 50%;
            top: 300px;
            margin-left: 600px;
            width: 45px;
            height: 130px;
            background-color: pink;
        }
        
        .w {
            width: 1200px;
            margin: 10px auto;
        }
        
        .header {
            height: 150px;
            background-color: purple;
        }
        
        .banner {
            height: 250px;
            background-color: skyblue;
        }
        
        .main {
            height: 1000px;
            background-color: yellowgreen;
        }
        
        span {
            display: none;
            position: absolute;
            bottom: 0;
        }
    </style>
</head>

<body>
    <div class="slider-bar">
        <span class="goBack">返回顶部</span>
    </div>
    <div class="header w">头部区域</div>
    <div class="banner w">banner区域</div>
    <div class="main w">主体部分</div>
    <script>
        //1. 获取元素
        var sliderbar = document.querySelector('.slider-bar');
        var banner = document.querySelector('.banner');
        // banner.offestTop 就是被卷去头部的大小 一定要写到滚动的外面
        var bannerTop = banner.offsetTop
            // 当我们侧边栏固定定位之后应该变化的数值
        var sliderbarTop = sliderbar.offsetTop - bannerTop;
        // 获取main 主体元素
        var main = document.querySelector('.main');
        var goBack = document.querySelector('.goBack');
        var mainTop = main.offsetTop;
        // 2. 页面滚动事件 scroll
        document.addEventListener('scroll', function() {
            // console.log(11);
            // window.pageYOffset 页面被卷去的头部
            // console.log(window.pageYOffset);
            // 3 .当我们页面被卷去的头部大于等于了 172 此时 侧边栏就要改为固定定位
            if (window.pageYOffset >= bannerTop) {
                sliderbar.style.position = 'fixed';
                sliderbar.style.top = sliderbarTop + 'px';
            } else {
                sliderbar.style.position = 'absolute';
                sliderbar.style.top = '300px';
            }
            // 4. 当我们页面滚动到main盒子，就显示 goback模块
            if (window.pageYOffset >= mainTop) {
                goBack.style.display = 'block';
            } else {
                goBack.style.display = 'none';
            }

        })
    </script>
```

## 7 mouseover and mouseenter

- 当鼠标移动到元素上时就会触发mouseenter 事件
- 类似 mouseover，它们两者之间的差别是
- mouseover 鼠标经过自身盒子会触发，经过子盒子还会触发。mouseenter  只会经过自身盒子触发
- 之所以这样，就是因为mouseenter不会冒泡
- 跟mouseenter搭配鼠标离开 mouseleave  同样不会冒泡

## 8 动画原理

```html
<style>
        div {
            position: absolute;
            left: 0;
            width: 100px;
            height: 100px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <div></div>
    <script>
        // 动画原理
        // 1. 获得盒子当前位置  
        // 2. 让盒子在当前位置加上1个移动距离
        // 3. 利用定时器不断重复这个操作
        // 4. 加一个结束定时器的条件
        // 5. 注意此元素需要添加定位， 才能使用element.style.left
        var div = document.querySelector('div');
        var timer = setInterval(function() {
            if (div.offsetLeft >= 400) {
                // 停止动画 本质是停止定时器
                clearInterval(timer);
            }
            div.style.left = div.offsetLeft + 1 + 'px';
        }, 30);
    </script>
</body>
```

### 8.1 简单函数封装动画

```html
<style>
        div {
            position: absolute;
            left: 0;
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        
        span {
            position: absolute;
            left: 0;
            top: 200px;
            display: block;
            width: 150px;
            height: 150px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <div></div>
    <span>夏雨荷</span>
    <script>
        // 简单动画函数封装obj目标对象 target 目标位置
        function animate(obj, target) {
            var timer = setInterval(function() {
                if (obj.offsetLeft >= target) {
                    // 停止动画 本质是停止定时器
                    clearInterval(timer);
                }
                obj.style.left = obj.offsetLeft + 1 + 'px';

            }, 30);
        }

        var div = document.querySelector('div');
        var span = document.querySelector('span');
        // 调用函数
        animate(div, 300);
        animate(span, 200);
    </script>
</body>

```

### 8.2 给不同对象添加不同的定时器

```html
    <style>
        div {
            position: absolute;
            left: 0;
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        
        span {
            position: absolute;
            left: 0;
            top: 200px;
            display: block;
            width: 150px;
            height: 150px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <button>点击夏雨荷才走</button>
    <div></div>
    <span>夏雨荷</span>
    <script>
        // var obj = {};
        // obj.name = 'andy';
        // 简单动画函数封装obj目标对象 target 目标位置
        // 给不同的元素指定了不同的定时器
        function animate(obj, target) {
            // 当我们不断的点击按钮，这个元素的速度会越来越快，因为开启了太多的定时器
            // 解决方案就是 让我们元素只有一个定时器执行
            // 先清除以前的定时器，只保留当前的一个定时器执行
            clearInterval(obj.timer);
            obj.timer = setInterval(function() {
                if (obj.offsetLeft >= target) {
                    // 停止动画 本质是停止定时器
                    clearInterval(obj.timer);
                }
                obj.style.left = obj.offsetLeft + 1 + 'px';

            }, 30);
        }

        var div = document.querySelector('div');
        var span = document.querySelector('span');
        var btn = document.querySelector('button');
        // 调用函数
        animate(div, 300);
        btn.addEventListener('click', function() {
            animate(span, 200);
        })
    </script>
</body>

```

# 六 Web APIs第六天

## 1 缓动动画

```HTML
<style>
        div {
            position: absolute;
            left: 0;
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        
        span {
            position: absolute;
            left: 0;
            top: 200px;
            display: block;
            width: 150px;
            height: 150px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <button>点击夏雨荷走</button>
    <div></div>
    <span>夏雨荷</span>
    <script>
        // 简单动画函数封装obj目标对象 target 目标位置
        var div = document.querySelector('div');
        var span = document.querySelector('span');
        var btn = document.querySelector('button');

        function animate(obj, target) {
            // 当我们不断的点击按钮，这个元素的速度会越来越快，因为开启了太多的定时器
            // 解决方案就是 让我们元素只有一个定时器执行
            // 先清除以前的定时器，只保留当前的一个定时器执行
            clearInterval(obj.timer);
            obj.timer = setInterval(function() {
                //步长写到定时器里面
                var temp = (target - obj.offsetLeft) / 10 // 分10步
                var step = Math.ceil(temp)
                if (obj.offsetLeft >= target) {
                    clearInterval(timer);
                }
                // 把每次加1 这个步长值改为一个慢慢变小的值  步长公式：(目标值 - 现在的位置) / 10

                obj.style.left = obj.offsetLeft + step + 'px';
            }, 15)
        }
        // 调用函数
        animate(div, 300)

        btn.addEventListener('click', function() {
                animate(span, 1000)
            })
            // 匀速动画 就是 盒子是当前的位置 +  固定的值 10 
            // 缓动动画就是  盒子当前的位置 + 变化的值(目标值 - 现在的位置) / 10）
    </script>
```

## 2 高阶函数

```html
 <script>
        //   高阶函数  把函数作为一个参数
        function fn(a) {
            // var a = function() {}
            a()
        }
        fn(function() {
            alert(666)
        })
    </script>
```

## 3 引用animate函数

```html
 <style>
        .sliderbar {
            position: fixed;
            right: 0;
            bottom: 100px;
            width: 40px;
            height: 40px;
            text-align: center;
            line-height: 40px;
            cursor: pointer;
            color: #fff;
        }
        
        .con {
            position: absolute;
            left: 0;
            top: 0;
            width: 200px;
            height: 40px;
            background-color: purple;
            z-index: -1;
        }
    </style>
    <script src="animate.js"></script>
</head>

<body>
    <div class="sliderbar">
        <span>←</span>
        <div class="con">问题反馈</div>
    </div>

    <script>
        // 1. 获取元素
        var sliderbar = document.querySelector('.sliderbar');
        var span = document.querySelector('span');
        var con = document.querySelector('.con');
        sliderbar.addEventListener('mouseenter', function() {
            animate(con, -160, function() {
                span.innerHTML = '→'
            })
        })

        sliderbar.addEventListener('mouseleave', function() {
            animate(con, 0,
                function() {
                    span.innerHTML = '←'
                })
        })
    </script>
</body>
```

## 4 触摸事件

```html
<style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <div></div>
    <script>
        // 1. 获取元素
        // 2. 手指触摸DOM元素事件
        // （1） 触摸元素 touchstart：  获取手指初始坐标，同时获得盒子原来的位置
        // （2） 移动手指 touchmove：  计算手指的滑动距离，并且移动盒子
        // （3） 离开手指 touchend:
        var div = document.querySelector('div');
        div.addEventListener('touchstar', function(e) {
            star = e.targetTouches[0].pageX

        })
        div.addEventListener('touchmove', function() {


        })
        div.addEventListener('touchend', function(e) {

            // console.log(e);
            // 当我们手指离开屏幕的时候，就没有了 touches 和 targetTouches 列表
            // 但是会有 changedTouches
            end = e.changedTouches[0].pageX
            console.log(star, end);
        })
    </script>
</body>
```

## 5 触摸拖动元素

```html
<style>
        div {
            position: absolute;
            left: 0;
            width: 100px;
            height: 100px;
            background-color: pink;
        }
    </style>
</head>

<body>
    <div></div>
    <script>
        // （1） 触摸元素 touchstart：  获取手指初始坐标，同时获得盒子原来的位置
        // （2） 移动手指 touchmove：  计算手指的滑动距离，并且移动盒子
        // （3） 离开手指 touchend:
        var div = document.querySelector('div');
        var startX = 0; //获取手指初始坐标
        var startY = 0;
        var x = 0; //获得盒子原来的位置
        var y = 0;
        div.addEventListener('touchstart', function(e) {
            //  获取手指初始坐标
            startX = e.targetTouches[0].pageX;
            startY = e.targetTouches[0].pageY;
            x = this.offsetLeft;
            y = this.offsetTop;
        });

        div.addEventListener('touchmove', function(e) {
            //  计算手指的移动距离： 手指移动之后的坐标减去手指初始的坐标
            var moveX = e.targetTouches[0].pageX - startX;
            var moveY = e.targetTouches[0].pageY - startY;
            // 移动我们的盒子 盒子原来的位置 + 手指移动的距离
            this.style.left = x + moveX + 'px';
            this.style.top = y + moveY + 'px';
            e.preventDefault(); // 阻止屏幕滚动的默认行为
        });
    </script>
</body>
```

## 6 筋斗云案例

```html
<style>
        * {
            margin: 0;
            padding: 0
        }
        
        ul {
            list-style: none;
        }
        
        body {
            background-color: black;
        }
        
        .c-nav {
            width: 900px;
            height: 42px;
            background: #fff url(images/rss.png) no-repeat right center;
            margin: 100px auto;
            border-radius: 5px;
            position: relative;
        }
        
        .c-nav ul {
            position: absolute;
        }
        
        .c-nav li {
            float: left;
            width: 83px;
            text-align: center;
            line-height: 42px;
        }
        
        .c-nav li a {
            color: #333;
            text-decoration: none;
            display: inline-block;
            height: 42px;
        }
        
        .c-nav li a:hover {
            color: white;
        }
        
        .cloud {
            position: absolute;
            left: 0;
            top: 0;
            width: 83px;
            height: 42px;
            background: url(images/cloud.gif) no-repeat;
        }
    </style>
    <script src="animate.js"></script>
    <script>
        window.addEventListener('load', function() {
            //获取元素
            var c_nav = document.querySelector('.c-nav');
            var cloud = document.querySelector('.cloud');
            var lis = document.querySelectorAll('li');
            // 2. 给所有的小li绑定事件 
            // 这个current 做为筋斗云的起始位置
            var current = 0;
            for (var i = 0; i < lis.length; i++) {
                lis[i].addEventListener('mouseenter', function() {
                    animate(cloud, this.offsetLeft);
                });
                lis[i].addEventListener('mouseleave', function() {
                    animate(cloud, current);
                });
                // (3) 当我们鼠标点击，就把当前位置做为目标值
                lis[i].addEventListener('click', function() {
                    current = this.offsetLeft;
                })
            }
        })
    </script>
</head>

<body>
    <div id="c_nav" class="c-nav">
        <span class="cloud"></span>
        <ul>
            <li><a href="#">首页新闻</a></li>
            <li><a href="#">师资力量</a></li>
            <li><a href="#">活动策划</a></li>
            <li><a href="#">企业文化</a></li>
            <li><a href="#">招聘信息</a></li>
            <li><a href="#">公司简介</a></li>
            <li><a href="#">我是佩奇</a></li>
            <li><a href="#">啥是佩奇</a></li>
        </ul>
    </div>
</body>
```



# 七 Web APIs第七天

## 1 classList的使用

```html
<style>
        .bg {
            background-color: black;
        }
    </style>
</head>

<body>
    <div class="one two"></div>
    <button> 开关灯</button>
    <script>
        // classList 返回元素的类名
        var div = document.querySelector('div');
        // console.log(div.classList[1]);
        // 1. 添加类名  是在后面追加类名不会覆盖以前的类名 注意前面不需要加.
        div.classList.add('three');
        // 2. 删除类名
        div.classList.remove('one');
        // 3. 切换类
        var btn = document.querySelector('button');
        btn.addEventListener('click', function() {
            document.body.classList.toggle('bg');
        })
    </script>
</body>
```

## 2 fastclick插件的使用

```html
<style>
        div {
            width: 50px;
            height: 50px;
            background-color: pink;
        }
    </style>
    <script src="fastclick.js"></script>
</head>

<body>
    <div></div>
    <script>
        if ('addEventListener' in document) {
            document.addEventListener('DOMContentLoaded', function() {
                FastClick.attach(document.body);
            }, false);
        }
        var div = document.querySelector('div');
        div.addEventListener('click', function() {
            alert(11);
        })
    </script>
</body>

```

## 3 本地存储

**1、本地存储特性**

- 数据存储在用户浏览器中
- 设置、读取方便、甚至页面刷新不丢失数据
- 容量较大，sessionStorage约5M、localStorage约20M
- 只能存储字符串，可以将对象JSON.stringify() 编码后存储

**2、window.sessionStorage**

- 生命周期为关闭浏览器窗口
- 在同一个窗口(页面)下数据可以共享
- 以键值对的形式存储使用

**3、window.localStorage**

- 声明周期永久生效，除非手动删除 否则关闭页面也会存在
- 可以多窗口（页面）共享（同一浏览器可以共享）
- 以键值对的形式存储使用

### 3.1 sessionStorage

```html
<body>
    <input type="text">
    <button class="set">存储数据</button>
    <button class="get">获取数据</button>
    <button class="remove">删除数据</button>
    <button class="del">清空所有数据</button>
    <script>
        console.log(localStorage.getItem('username'));

        var ipt = document.querySelector('input');
        var set = document.querySelector('.set');
        var get = document.querySelector('.get');
        var remove = document.querySelector('.remove');
        var del = document.querySelector('.del');
        set.addEventListener('click', function() {
            // 当我们点击了之后，就可以把表单里面的值存储起来
            var val = ipt.value;
            sessionStorage.setItem('uname', val);
            sessionStorage.setItem('pwd', val);
        });
        get.addEventListener('click', function() {
            // 当我们点击了之后，就可以把表单里面的值获取过来
            console.log(sessionStorage.getItem('uname'));

        });
        remove.addEventListener('click', function() {
            // 
            sessionStorage.removeItem('uname');

        });
        del.addEventListener('click', function() {
            // 当我们点击了之后，清除所有的
            sessionStorage.clear();

        });
    </script>
</body>
```

### 3.2 localStorage

```html
<body>
    <input type="text">
    <button class="set">存储数据</button>
    <button class="get">获取数据</button>
    <button class="remove">删除数据</button>
    <button class="del">清空所有数据</button>
    <script>
        var ipt = document.querySelector('input');
        var set = document.querySelector('.set');
        var get = document.querySelector('.get');
        var remove = document.querySelector('.remove');
        var del = document.querySelector('.del');
        set.addEventListener('click', function() {
            var val = ipt.value;
            localStorage.setItem('username', val);
        })
        get.addEventListener('click', function() {
            console.log(localStorage.getItem('username'));

        })
        remove.addEventListener('click', function() {
            localStorage.removeItem('username');

        })
        del.addEventListener('click', function() {
            localStorage.clear();

        })
    </script>
</body>
```

### 3.3 本地存储案例-记住用户名

```html
<body>
    <input type="text" id="username"> <input type="checkbox" name="" id="remember"> 记住用户名
    <script>
        var username = document.querySelector('#username');
        var remember = document.querySelector('#remember');
        if (localStorage.getItem('username')) {
            username.value = localStorage.getItem('username');
            remember.checked = true;
        }
        remember.addEventListener('change', function() {
            if (this.checked) {
                localStorage.setItem('username', username.value)
            } else {
                localStorage.removeItem('username');
            }
        })
    </script>
</body>
```

