# 一 JS基础第一天

## 1 JS初识

### 1.1 js三种写法

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script>
        // 2 内嵌式
        // alert('沙漠骆驼');
    </script>
    <script src="js/my.js"></script>
</head>

<body>
    <!-- 1 行内式 -->
    <!-- <input type="button" value="login" onclick="alert('秋香')"> -->
</body>

</html>
```

### 1.2 js输出语句

```html
<script>
        // 用户输入框
        prompt('请输入姓名');
        // 网页警示框
        alert('这是警示框');
        console.log('这是程序员看到的');
    </script>
```

## 2 变量

### 2.1 变量的写法

```html
<script>
        // 用户输入框
        prompt('请输入姓名');
        // 网页警示框
        alert('这是警示框');
        console.log('这是程序员看到的');
    </script>
```

### 2.2 变量语法拓展

```html
<script>
        // 1  变量更新
        var myname = 'pink';
        console.log(myname);
        myname = 'dili';
        //2 声明多个变量
        var age = 18;
        address = '火影村';
        salary = 2000;
        // 3. 声明变量的特殊情况
        // 3.1 只声明不赋值 结果是？  程序也不知道里面存的是啥 所以结果是 undefined  未定义的
        var sex;
        console.log(sex); // undefined
        // 3.2  不声明 不赋值 直接使用某个变量会报错滴
        // console.log(tel);
        // 3.3 不声明直接赋值使用
        qq = 110;
        console.log(qq);
    </script>
```

### 2.3 交换两个变量

```html
<script>
        // js 是编程语言有很强的逻辑性在里面： 实现这个要求的思路 先怎么做后怎么做 
        // 1. 我们需要一个临时变量帮我们
        // 2. 把apple1 给我们的临时变量 temp 
        // 3. 把apple2 里面的苹果给 apple1 
        // 4. 把临时变量里面的值 给 apple2 
        var temp; // 声明了一个临时变量为空
        var apple1 = '青苹果';
        var apple2 = '红苹果';
        temp = apple1; // 把右边给左边
        apple1 = apple2;
        apple2 = temp;
        console.log(apple1);
        console.log(apple2);
    </script>
```

### 2.4 变量的数字类型

```html
 <script>
        // int num = 10;  java 
        // var num; // 这里的num 我们是不确定属于哪种数据类型的
        var num = 10; // num 属于数字型 
        // js 的变量数据类型是只有程序在运行过程中，根据等号右边的值来确定的
        var str = 'pink'; // str 字符串型
        // js是动态语言 变量的数据类型是可以变化的
        var x = 10; // x 是数字型 
        x = 'pink'; // x 字符串型
    </script>
```

## 3 数据类型

### 3.1 变量的数据类型

```html
<script>
        // int num = 10;  java 
        // var num; // 这里的num 我们是不确定属于哪种数据类型的
        var num = 10; // num 属于数字型 
        // js 的变量数据类型是只有程序在运行过程中，根据等号右边的值来确定的
        var str = 'pink'; // str 字符串型
        // js是动态语言 变量的数据类型是可以变化的
        var x = 10; // x 是数字型 
        x = 'pink'; // x 字符串型
    </script>
```

3.2 数据类型Number

```HTML
 <script>
        var num = 10; // num 数字型 
        var PI = 3.14 // PI 数字型
            // 1. 八进制  0 ~ 7  我们程序里面数字前面加0 表示八进制
        var num1 = 010;
        console.log(num1); //  010  八进制 转换为 10进制 就是  8 
        var num2 = 012;
        console.log(num2);
        // 2. 十六进制  0 ~ 9  a ~ f    #ffffff  数字的前面加 0x 表示十六进制
        var num3 = 0x9;
        console.log(num3);
        var num4 = 0xa;
        console.log(num4);
        // 3. 数字型的最大值
        console.log(Number.MAX_VALUE);
        // 4. 数字型的最小值
        console.log(Number.MIN_VALUE);
        // 5. 无穷大
        console.log(Number.MAX_VALUE * 2); // Infinity 无穷大  
        // 6. 无穷小
        console.log(-Number.MAX_VALUE * 2); // -Infinity 无穷大
        // 7. 非数字
        console.log('pink老师' - 100); // NaN
    </script>
```

### 3.2  isNaN

```HTML
<script>
        // isNaN() 这个方法用来判断非数字   并且返回一个值 如果是数字返回的是 false 如果不是数字返回的是true
        console.log(isNaN(12)); // false
        console.log(isNaN('pink老师')); // true
    </script>
```

### 3.3 字符串型string

```html
 <script>
        // 'pink'   'pink老师'  '12'   'true'
        var str = '我是一个"高富帅"的程序员';
        console.log(str);
        // 字符串转义字符  都是用 \ 开头 但是这些转义字符写道引号里面
        var str1 = "我是一个'高富帅'的\n程序员";
        console.log(str1);
    </script>
```

### 3.4 字符串长度及拼接

```html
<script>
        // 字符串的相加
        var str = '今天' + '周三';
        console.log(str);
        var str = '今天' + 23; //字符串加数值还是字符串；
        console.log(str);
        // 拼接方式一
        var line = '周五'
        var str = '今天是' + line + '，天气晴'; //引引++  ' + 变量 + '
        console.log(str);
        // 拼接方式二
        var line = '周五'
        var str = `今天是${line}，天气晴`; // ``符号，然后中间使用${变量}；
        console.log(str);
    </script>
```

### 3.5 Boolean布尔型

```html
<script>
        // 1 布尔型 
        var flag = true;
        var flag1 = false;
        console.log(flag + 1); // ture is 1
        console.log(flag1 + 1); // false is 0
        // Undefined  没有赋值的变量
        var mum = undefined
        console.log(mum + 1); //NaN
        console.log(mum + '这是一个字符串'); // undefined这是一个字符串
        // null 空值
        var shu = null;
        console.log(shu + 1); // 1 
        console.log(shu + '字符串'); // null字符串
    </script>
```

### 3.6 typeof 监测数据类型

```html
<script>
        var mum = 18;
        console.log(typeof mum); // number
        var under = undefined;
        console.log(typeof under); //unfenied
        var falg = null;
        console.log(typeof falg); // object
        var str = 'jessica';
        console.log(typeof str); // 字符串
    </script>
```

### 3.7  转换成字符串

```html
 <script>
        // 1----转换成字符串
        // var age = prompt('请输入年龄');
        // alert('您的年龄是' + age + '岁');
        // console.log('您的年龄是' + age + '岁');
        // 方法一、 toString()
        var age = 10;
        var str = age.toString();
        console.log(str); // 黑色
        // 方法二、String()
        var mum = 20;
        var _str = String(mum);
        console.log(_str);
        // 方法三、 加字符串 '';
        var m = 20;
        var _m = '' + 变量;
        console.log(_m);
    </script>
```

### 3.8  转换成数字类型

```html
<script>
        // var age = prompt('请输入年龄');
        // console.log(parseInt(age));
        // 转换成数字
        // 方法一  parseInt(变量)  取整
        console.log(parseInt('3.14')); //3
        console.log(parseInt('1.5')); //1
        console.log(parseInt('150px')); //150
        console.log(parseInt('rem150px')); //NaN
        // 方法二  parseFloat(变量)  浮点
        console.log(parseFloat('3.14')); //  3.14
        console.log(parseInt('150px')); //150
        console.log(parseInt('rem150px')); //NaN
        // 方法三  Number()
        console.log(Number('12')); // 12
        // 方法四  隐式转换  利用算数运算 - * /
        console.log('120' - '113'); // 7
    	// 方法五  在变量前加+
    	+prompt()
    </script>
```

### 3.9 转换成布尔值

```html
 <script>
        // 以下都是false
        console.log(Boolean(0));
        console.log(Boolean());
        console.log(Boolean(NaN));
        console.log(Boolean(null));
        console.log(Boolean(undefined));
        // 以下都是true
        console.log(Boolean('123'));
        console.log(Boolean('hello'));
        // 所有的数字全为真，0为假；  所有的字符串全为真，''为假；
    </script>
```



## 4 案例

### 4.1 计算年龄

```html
<script>
        var year = prompt('请输入您的出生年份');
        var age = 2019 - year;
        alert(`您今年已经${age}岁了`);
    </script>
```

### 4.2 简单加法

```html
<script>
        // 先输入第一个值，然后保存
        // 再输入第二个值，然后保存
        // 接着让前两个值相加，这里要把前两个值转换成数字型
        // 最后输出结果
        var num1 = prompt('请输入第一个值：');
        var num2 = prompt('请输入第二个值：');
        // 方法一 
        // var result = parseFloat(num1) + parseFloat(num2);
        // 方法二 加+
        var result = ((+num1) + (+num2));
        alert('您的结果是：' + result);
    </script>
```

### 4.3 数据统计

```html
 <script>
        // 输入姓名
        // 输入年龄
        // 输入性别
        // 最后综合弹出
        var _name = prompt('请输入名字：');
        var age = prompt('请输入年龄：');
        var sex = prompt('请输入性别:');
        var result = '您的姓名是：' + _name + '\n您的年龄是：' + age + '\n您的性别是：' + sex;
        // alert('您的姓名是：' + _name + '\n您的年龄是：' + age + '\n您的性别是：' + sex);
        alert(result);
    </script>
```

# 二 JS基础第二天

## 1 运算符

- 算数运算符
- 递增和递减运算符
- 比较运算符
- 逻辑运算符
- 赋值运算符

### 1.1 算数运算符

```js
 // 取余
        console.log(2 % 5); // 2
        console.log(3 % 4); // 3
// 浮点数  特别注意，浮点数的最高精度是17位小数，不能直接判断两个浮点数是否相等
        console.log(2.1 + 2.2); // 4.300000000000001
```

### 1.2 递增和递减运算符

```js
		// 前置++  类似于 变量 +1   先赋值 再返回
        var age = 10;
        ++age;
        console.log(age + 10); // 21

        //------------------------------------

        //  后置++  先返回，再赋值
        var age = 5;
        age++;
        console.log(age++ + 10); // 16

        console.log(age); // 7

        // 前置后置综合练习

        var a1 = 12;
        var sum = ++a1 + a1++;
        // ++a1= 13 此时 a1=13
        // a1++=13
        // sum=13+13=26;
        console.log(sum);

        var a2 = 14;
        var a3 = a2++ + ++a2;
        // a2++=14 ,此时a2=15;
        // ++a2=16
        // a3=14+16=30
        console.log(a3);


        var num = 20;
        var sum = ++num + num++;
        // ++num = 21 此时num = 21
        // num++ = 21;
        console.log(sum); // 42

        var a = 4;
        // a++ = 4, 此时a=5;
        // ++a = 6;
        var b = a++ + ++a;
        console.log(b); // 10
```

### 1.3 比较运算符

```html
<script>
        console.log(3 > 5); // false
        console.log(3 < 5); // true

        console.log(3 >= 2); // true

        // 等于符号 ==  默认转换数据类型
        console.log(3 == 5); // false
        console.log(3 == 3); // true
        console.log(18 == '18'); // true
        console.log('qq' == '13'); // false


        // 不等于 !=
        console.log(18 != 18); //false
        console.log(3 != 3); // false
        console.log(3 != 4); // true

        // 全等于 ===  两边数类型完全一致
        console.log(18 === 18); // true
        console.log(18 === '18'); // flase

        // 并 && and
        console.log(3 > 5 && 3 > 2); //  flase
        console.log(3 > 1 && 3 > 2); //  true
        // 或 ||  or
        console.log(3 > 5 || 3 > 2); // ture

        // != 非  not
        console.log(!true); // false
    </script>
```

### 1.4 逻辑运算符

```html
<script>
        // and 左边为真，返回右边
        console.log(3 && 8); // 8
        // 左边为假，返回左边假 即为假，（一方为假 即假）
        console.log(0 && 8); //0
        console.log(1 && 3); //3
        console.log(3 && 0); //0



        // || or 左边为真 ，返回左边   （一方为真，即真）
        console.log(3 || 8); // 3
        // 左边为假，返回右边）
        console.log(0 || 8);
        console.log(5 || 4); //5
        console.log(0 || 3); //3
    </script>
```

### 1.5 赋值运算符

```html
<script>
        var num = 10;
        // 加 2
        console.log(num += 2); //12
        // 乘以2
        console.log(num *= 2); //24
        //除以2
        console.log(num /= 2); //12
        // 取余
        console.log(num %= 5); // 2
    </script>
```

### 1.6 if语句

```html
<script>
        if (88) { // true
            alert('666');
        }
        if (0) { // false
            alert('333');
        }
        if (undefined) { // false
            alert('222');
        }
        if ('显示') {
            alert('真的显示了');
        }

        var answer = prompt('你喜欢我吗？');
        if (answer == '是') {
            alert('我也喜欢你哦')
        } else {
            alert('竟然不喜欢本宝宝')
        }

        var speak = prompt('你是不是人');
        if (speak === '是') {
            alert('原来你是人');
        } else {
            alert('你不是人啊');
        }
    </script>
```

## 2 流程控制

### 2.1 三元表达式

```html
<script>
        // var age = prompt('请输入年龄')
        // var result = age > 18 ? '成年' : '未成年';
        // alert(result)

        // 数字小于10 前面自动补0
        var num = prompt('请输入0~59之间的数字');
        var result = num < 10 ? '0' + num : num;
        alert(result);
    </script>
```

### 2.2 switch

```js
// 1. switch 语句也是多分支语句 也可以实现多选1
        // 2. 语法结构 switch 转换、开关  case 小例子或者选项的意思
        // switch (表达式) {
        //     case value1:
        //         执行语句1;
        //         break;
        //     case value2:
        //         执行语句2;
        //         break;
        //         ...
        //         default:
        //             执行最后的语句;
        // }
        // 3. 执行思路  利用我们的表达式的值 和 case 后面的选项值相匹配 如果匹配上，就执行该case 里面的语句  如果都没有匹配上，那么执行 default里面的语句
        // 4. 代码验证
        switch (5) {
            case 1:
                console.log('这是1');
                break;
            case 2:
                console.log('这是2');
                break;
            case 3:
                console.log('这是3');
                break;
            default:
                console.log('其他');

        }
    </script>
```

### 2.3 利用switch进行比较运算

```html
<script>
        // 利用switch进行比较运算  加上(true)
        var money = parseInt(prompt('你有多少钱'));

        switch (true) {
            case (money <= 500):
                alert('请把钱带够');
                break;
            case (money <= 1000):
                alert('请你们吃棒棒糖');
                break;
            case (money <= 1500):
                alert('吃西瓜');
                break;
            case (money <= 2000):
                alert('鸡腿');
            default:
                alert('猪蹄');
        }
      </script>
```

**注：**

（1）switch后面小括号中是一个表达式，可以计算出一个值。

（2）大括号中，每一个case后面也有一个表达式，同样可以计算出一个值。

（3）switch后面表达式的值会与case后面表达式的值比较，如果相同，那么执行对应case后面的代码。

（4）case后面代码执行完毕之后，如果后面有break，则直接跳出整个switch语句。

（5）如果没有break，则继续进行switch和case后面表达式的比较，然后如此反复。

（6）当switch后面小括号里面是true，case后面就能用判断语句进行表达；只不过这种结构不如if -else简介

特别说明：default比较贪婪，只要给它机会，后面的语句就会被执行，比如它前面的条件都不满足，default后面的语句就获得执行的机会，还有即便前面有满足条件的case，但是没有break出语句，那么default后面的语句也会执行，把握机会能力比较强。

## 3 案例

### 3.1 if计算是否为闰年

```html
<script>
        // 算法：能被4整除且不能整除100的为闰年（如2004年就是闰年，1901年不是闰年）或者能够被 400 整除的就是闰年
        // 弹出prompt 输入框，让用户输入年份，把这个值取过来保存到变量中
        // 使用 if 语句来判断是否是闰年，如果是闰年，就执行 if 大括号里面的输出语句，否则就执行 else里面的输出语句
        // 一定要注意里面的且 &&  还有或者 || 的写法，同时注意判断整除的方法是取余为 0
        var year = prompt('请输入年份');
        if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
            alert('闰年');
        } else {
            alert('平年');
        }
    </script>
```

### 3.2 switch水果案例

```html
 <script>
        var fruit = prompt('请输入您要的水果');
        switch (fruit) {
            case '苹果':
                alert('苹果2块钱一斤');
                break;
            case '草莓':
                alert('草莓3块钱一斤');
                break;
            default:
                alert('没有该水果');

        }
    </script>
```

### 3.3 三元表达式-两个数字比较

```html
 <script>
        // 此案例可运用三元表达式
        var num1 = parseInt(prompt('请输入第一个值'));
        var num2 = parseInt(prompt('请输入第二个值'));
        // 此时num 是字符串形式，系统会默认比较字符串的大小，所以会出现 输入200  和 45  ，输出结果是45的情况
        // 需将num转换成数字形式，再进行比较
        var result = num1 > num2 ? num1 : num2;
        alert(result)
    </script>
```

### 3.4 if判断奇偶数

```html
<script>
        var a = prompt('请输入一个数字');
        if (a % 2 === 1) {
            alert('奇数');
        } else {
            alert('偶数');
        }
    </script>
```

### 3.5 if 判断星期几

```html
<script>
        var a = prompt('请输入今天几号了');
        if (a % 7 === 1) {
            alert('今天星期三了');

        } else if (a % 7 === 2) {
            alert('今天星期四了');

        } else if (a % 7 === 3) {
            alert('今天星期五了');

        } else if (a % 7 === 4) {
            alert('今天星期六了');

        } else if (a % 7 === 5) {
            alert('今天星期天了');

        } else if (a % 7 === 6) {
            alert('今天星期一了');

        } else if (a % 7 === 7) {
            alert('今天星期二了');

        }
    </script>
```

# 三 JS基础第三天

## 1 循环

### 1.1 for循环

1、 for循环执行相同的语句

```js
  var sum = prompt('请输入循环的次数');
        for (var a = 1; a <= sum; a++) {
            console.log('HELLO');

        }
```

2、 for循环执行不同的语句

```js
 var age = +prompt('请输入年龄');
        for (var a = 1; a <= age; a++) {
            if (age === 1) {
                alert('出生');

            } else if (age === 90) {
                alert('死了');
            } else {
                alert(`你今年${age}岁了`);
            }
        }
```

### 1.2 双重for循环

```js

        // - 内层循环可以看做外层循环的语句
        // - 内层循环执行的顺序也要遵循 for 循环的执行顺序 
        // - 外层循环执行一次，内层循环要执行全部次数
        for (var a = 1; a <= 4; a++) {
            console.log('这是外层循环第' + a + '次');

            for (var b = 1; b <= 4; b++) {
                console.log('这是内层循环第' + b + '次');

            }
        }
// 打印3行3列星星的案例
	<script>
        var str = '';
        for (var a = 1; a <= 3; a++) {
            for (var b = 1; b <= 3; b++) {
                str = str + '☆';

            }
            str = str + '\n';
        }
        console.log(str);
    </script>

```

**for循环小结**

- for 循环可以重复执行某些相同代码
- for 循环可以重复执行些许不同的代码，因为我们有计数器
- for 循环可以重复执行某些操作，比如算术运算符加法操作
- 随着需求增加，双重for循环可以做更多、更好看的效果
- 双重 for 循环，外层循环一次，内层 for 循环全部执行
- for 循环是循环条件和数字直接相关的循环

### 1.3 while语句

```js
while (条件表达式) {
    // 循环体代码 
}
```

```js
// 使用 while 循环时一定要注意，它必须要有退出条件，否则会成为死循环
        var num = 1;
        while (num <= 100) {
            console.log('OK');
            num++
        }

        // 计算1-100之和

        var message = prompt('你爱我吗？');

        while (message !== '我爱你') {
            message = prompt('你爱我吗');
        }
        alert('我也爱你呦');

       
```

- 先执行条件表达式，如果结果为 true，则执行循环体代码；如果为 false，则退出循环，执行后面代码

- 执行循环体代码

- 循环体代码执行完毕后，程序会继续判断执行条件表达式，如条件仍为true，则会继续执行循环体，直到循环条件为 false 时，整个循环过程才会结束

  **注意**：

- 使用 while 循环时一定要注意，它必须要有退出条件，否则会成为死循环

- while 循环和 for 循环的不同之处在于 while 循环可以做较为复杂的条件判断，比如判断用户名和密码

### 1.4 do while 语句

```js
do {
    // 循环体代码 - 条件表达式为 true 时重复执行循环体代码
} while(条件表达式);
```

```js
 // do while 语句
        var a = 1;
        do {
            console.log('最近好吗');

        } while (a <= 100);
```

- 先执行一次循环体代码 
- 再执行条件表达式，如果结果为 true，则继续执行循环体代码，如果为 false，则退出循环，继续执行后面代码	
- 注意：先再执行循环体，再判断，do…while循环语句至少会执行一次循环体代码

### 1.5 continue and break

**continue** 关键字用于立即跳出本次循环，继续下一次循环（本次循环体中 continue 之后的代码就会少执行一次）

**break** 关键字用于立即跳出整个循环（循环结束）

```js
// continue 退出当前循环次数，继续执行剩余的次数
        for (var a = 1; a <= 5; a++) {
            if (a == 3) {
                continue;
            }
            console.log('我吃第' + a + '个包子');

        }

        // 求1-100之间，能被7整除之外的数之和
        var sum = 0;
        for (var b = 1; b <= 100; b++) {
            if (b % 7 === 0) {
                continue;
            }
            sum = sum + b;
        }
        console.log(sum);
```

```js
// 退出全部循环，剩余的循环也不执行
        for (var a = 1; a <= 5; a++) {
            if (a == 4) {
                break;
            }
            console.log(`我吃第${a}个包子`);

        }
```



## 2 案例

### 2.1 for求和案例

```js
<script>
        // 求1-100的和
        var sum = 0;
        for (var a = 1; a <= 100; a++) {
            // 第一次 a =1  sum=0+1=1
            // 第二次 a=2 sum=0+1+2=3;
            // 第三次 a=3 sum=0+1+2+3=6;

            sum = sum + a;
        }
        console.log(sum);

        // 求1-100 的平均数

        var odd = 0,
            even = 0;
        for (var a = 1; a <= 100; a++) {
            if (a % 2 === 0) {
                even = even + a; //evev += a;

            } else {
                odd = odd + a;
            }
        }
        console.log(even, odd);

        // 求1-100之间能被3整除的数的和

        var num = 0;
        for (var a = 1; a <= 100; a++) {
            if (a % 3 === 0) {
                num += a;
            }
        }
        console.log(num);

        // 求1-100之间除了能被9整除的数之和

        var sum1 = 0;
        for (var a = 1; a <= 100; a++) {
            if (a % 9 === 0) {
                continue;
            }
            sum1 = sum1 + a;
        }
        console.log(sum1);
    </script>
```

### 2.1 打印正倒三角案例

```js
 // 打印正三角
// 方法一  
        var str = '';
        for (var a = 1; a <= 5; a++) {
            for (var b = 1; b <= 5 - a; b++) {
                str = str + '☆';
            }
            str = str + '\n';
        }
        console.log(str);

        // 方法二
        var str = '';
        for (var a = 1; a <= 5; a++) {
            for (var b = a; b <= 5; b++) {
                str = str + '☆';
            }
            str = str + '\n';
        }
        console.log(str);

	// 打印正三角
 	var str = '';
        for (var a = 1; a <= 10; a++) {
            for (var b = 1; b <= a; b++) {
                // str = str + '☆';
                str = str + '☆';

            }
            str = str + '\n';
        }
        console.log(str);
```

### 2.3 while and do while 语句案例

```js
<script>
    // 要求：接收用户输入的用户名和密码，若用户名为 “admin” ,密码为 “123456” ,则提示用户登录成功!  否则，让用户一直输入。
        // while 语句写法
        var username = prompt('请输入用户名：');
        var password = prompt('请输入密码：');
        while (username !== 'admin' && password !== 123456) {
            username = prompt('请输入用户名：');
            password = prompt('请输入密码：');
        }
        alert('登录成功');

        // do while 语句写法
        do {
            var username = prompt('请输入用户名：');
            var password = prompt('请输入密码：');
        } while (username !== 'admin' && password !== 123456) // 如果不满足while条件，则继续执行
        alert('登录成功');
    </script>
```

### 2.4 ATM

```js
// 里面现存有 100 块钱。

        // 如果存钱， 就用输入钱数加上先存的钱数, 之后弹出显示余额提示框
        // 如果取钱， 就减去取的钱数， 之后弹出显示余额提示框
        // 如果显示余额， 就输出余额
        // 如果退出， 弹出退出信息提示框
        var yve = 100;

        var shuru = prompt(`请输入您要的操作：\n 1.存钱\n 2.取钱\n 3.显示余额\n 4.退出`);
        while (shuru != '退出') {
            // var shuru = prompt(`请输入您要的操作：\n 1.存钱\n 2.取钱\n 3.显示余额\n 4.退出`);
            if (shuru == '存钱') {
                yve += +parseInt(prompt('请输入存入金额'));

                alert(`余额是：${yve}元`);
            } else if (shuru == '取钱') {
                yve -= +parseInt(prompt('请输入取钱金额'));

                alert(`余额是：${yve}元`);
            } else if (shuru == '显示余额') {
                alert(`余额是：${yve}元`);
            }
            var shuru = prompt(`请输入您要的操作：\n 1.存钱\n 2.取钱\n 3.显示余额\n 4.退出`);

        }
        alert(`完成`);
```



# 四 JS基础第四天

## 1 数组

### 1.1 创建数组

```js
		// 方法一  添加new创建数组
       var num = new Array();// 创建一个空的数组

        // 方法二  添加字面量创建数组

        // var num = [] // 创建一个空的数组
        var num = [1, 2, 'hello', true];
		// 获取数组中的元素
        console.log(num);
        console.log(num[0]); // 1
        console.log(num[1]); // 2
        console.log(num[2]); // hello
        console.log(num[3]); // true
        console.log(num[4]); // undefined
```

### 1.2 遍历数组

```js
 // 遍历数组：就是把数组的元素从头到尾访问一次
        var arr = ['小红', '小明', '小黄', '小吕'];
        for (var a = 0; a < 4; a++) {
            console.log(arr[a]);

        }
        console.log(arr.length);

        // 1. 因为我们的数组索引号从0开始 ，所以 a 必须从 0开始  a < 3
        // 2. 输出的时候 arr[a]  a 计数器当索引号来用

        // 数组的长度
        var arr = ['小红', '小明', '小黄', '小吕'];
        for (var a = 0; a < arr.length; a++) {
            console.log(arr[a]);

        }
        // 1. 数组的长度是元素个数  不要跟索引号混淆
        // 2. arr.length 动态监测数组元素的个数

        var arr = ['小红', '小明', '小黄', '小吕'];
        for (var a = 0; a < arr.length; a++) {
            console.log(arr[a]);

        }
```

### 1.3 数组的运算

```js
		// 1. 求数组 [2,6,1,7, 4] 里面所有元素的和以及平均值。
        // (1)声明一个求和变量 sum。
        // (2)遍历这个数组，把里面每个数组元素加到 sum 里面。
        // (3)用求和变量 sum 除以数组的长度就可以得到数组的平均值。
        var arr = [2, 5, 50, 87, 60, 99, 50];
        var sum = 0;
        var ave = 0;
        for (var a = 0; a < arr.length; a++) {
            sum = arr[a];

        }
        ave = sum / arr.length;
        console.log(sum, ave);

        // 求数组[2,6,1,77,52,25,7]中的最大值
        // 声明一个保存最大元素的变量 max。
        // 默认最大值可以取数组中的第一个元素。
        // 遍历这个数组，把里面每个数组元素和 max 相比较。
        // 如果这个数组元素大于max 就把这个数组元素存到 max 里面，否则继续下一轮比较。
        // 最后输出这个 max

        var arr = [2, 5, 50, 87, 60, 99, 50];
        var max = arr[0];
        for (var a = 1; a < arr.length; a++) {
            if (arr[a] > max) {
                max = arr[a];
            }
        }
        console.log('最大值是' + max);

		// 加分隔符 
        var arr = ['xiaoming', 'xiaoli', 'xiaoliu'];
        var sum = '';
        var stp = '|';
        for (var a = 0; a < arr.length; a++) {
            sum = sum + arr[a] + stp;

        }
        console.log(sum);

```

### 1.4 数组筛选、去重、splice

```js
// 新建一个数组，里面存放10个整数（ 1~10）
        // 核心原理：使用循环来追加数组。
        // 1、声明一个空数组 arr。
        // 2、循环中的计数器 i  可以作为数组元素存入。
        // 3、由于数组的索引号是从0开始的， 因此计数器从 0 开始更合适，存入的数组元素要+1。
        var arr = [];
        for (var a = 0; a < 10; a++) {
            // arr = i; 不要直接给数组名赋值 否则以前的元素都没了
            arr[a] = a + 1;
        }
        console.log(arr);

// 将数组 [2, 0, 6, 1, 77, 0, 52, 0, 25, 7] 中大于等于 10 的元素选出来，放入新数组。
        // 1、声明一个新的数组用于存放新数据newArr。
        // 2、遍历原来的旧数组， 找出大于等于 10 的元素。
        // 3、依次追加给新数组 newArr。
        // 方法一
        var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
        var newArr = [];
        var b = 0;
        for (var a = 0; a < arr.length; a++) {
            if (arr[a] >= 10) {
                newArr[b] = arr[a];
                b++;
            }
        }
        console.log(newArr);

 // 将数组[2, 0, 6, 1, 77, 0, 52, 0, 25, 7]中的 0 去掉后，形成一个不包含 0 的新数组。
        // 1、需要一个新数组用于存放筛选之后的数据。
        // 2、遍历原来的数组， 把不是 0 的数据添加到新数组里面(此时要注意采用数组名 + 索引的格式接收数据)。
        // 3、新数组里面的个数， 用 length 不断累加。
        var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
        var newArr = [];
        for (var a = 0; a < arr.length; a++) {
            if (arr[a] !== 0) {
                newArr[newArr.length] = arr[a];
            }
        }
        console.log(newArr);

// splice的使用
var arr1 = [1, 2, 'pink老师', true, [666]]
        // arr1[3] = 'purple'
        // splice(开始删除位置的索引, 要删除几项, 是否补位)
        arr1.splice(1, 2, 9999999999, 88888888)
        console.log(arr1)
```

### 1.5 翻转数组、冒泡排序

```js
// 将数组 ['red', 'green', 'blue', 'pink', 'purple'] 的内容反过来存放
        // 1、声明一个新数组 newArr
        // 2、把旧数组索引号第4个取过来（arr.length - 1)，给新数组索引号第0个元素 (newArr.length)
        // 3、我们采取 递减的方式  i--
        var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
        var newArr = [];
        for (var a = arr.length - 1; a >= 0; a--) {
            newArr[newArr.length] = arr[a];
        }
        console.log(newArr);
// 翻转数组 方法二 
		var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];
        var newArr = [];
        for (var i = 0; i < arr.length; i++) {
            newArr[i] = arr[arr.length - i - 1]

        }
        console.log(newArr);

 // 冒泡排序
        // var arr = [5, 4, 3, 2, 1];
        var arr = [4, 1, 2, 3, 5];
        for (var i = 0; i <= arr.length - 1; i++) { // 外层循环管趟数 
            for (var j = 0; j <= arr.length - i - 1; j++) { // 里面的循环管 每一趟的交换次数
                // 内部交换2个变量的值 前一个和后面一个数组元素相比较
                if (arr[j] < arr[j + 1]) {
                    var temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }

            }
        }
        console.log(arr);
```

## 2 函数

### 2.1 函数的使用

```js
// 函数使用分为两步： 声明函数 和 调用函数
        // 1. 声明函数
        // function 函数名() {
        //     // 函数体
        // }
        function sayHi() {
            console.log('hi~~');

        }
        // (1) function 声明函数的关键字 全部小写
        // (2) 函数是做某件事情，函数名一般是动词 sayHi 
        // (3) 函数不调用自己不执行
        // 2. 调用函数
        // 函数名();
        sayHi();
        // 调用函数的时候千万不要忘记加小括号


```

### 2.2 带参数的函数

```js
 // 函数执行相同的代码
        function cook() {
            console.log('周天');

        }
        cook();
        cook();

        // 函数执行不同的代码
        function step(date) {
            console.log(date);

        }
        step('周三');
        step('周六');
```

### 2.3 函数求和

```js
 // 函数求两个数之和
        function getSum(num1, num2) {
            console.log(num1 + num2);
        }
        getSum(2, 6);
        getSum(1, 100);


        // 函数求两个数之间的和
        function getSum(num3, num4) {
            var sum = 0;
            for (var a = num3; a <= num4; a++) {
                sum = sum + a;

            }
            console.log(sum);

        }
        getSum(2, 6);
        getSum(1, 100);
```

### 2.4 函数的返回值

```js
 // - 在使用 return 语句时，函数会停止执行，并返回指定的值
        // - 如果函数没有 return ，返回的值是 undefined
        function getSum(num1, num2) {
            return num1 + num2;
        }
        console.log(getSum(1, 5));
        console.log(getSum(-6, 5));

        // 函数求两个数的最大值
        // 三元表达式
        function getMaxSum(num1, num2) {
            return num1 > num2 ? num1 : num2;
        }
        console.log(getMaxSum(1, 8));
        
        // if 语句
        function getMaxSum(num1, num2) {
            if (num1 > num2) {
                return num1;
            } else {
                return num2;
            }
        }
        console.log(getMaxSum(1, 6));
	// 运算	
	 function getSum(num1, num2) {
            return [num1 + num2, num1 - num2, num1 / num1, num1 * num2] //  执行多项操作，使用数组
        }
        var re = getSum(6, 2);
        console.log(re);
```

### 2.5 获取函数的最大值

```js
<script>
        // 利用函数求数组 [5,2,99,101,67,77] 中的最大数值。

        function getMaxSum(arr) {

            var max = arr[0];
            for (var a = 1; a < arr.length; a++) {
                if (arr[a] > max) {
                    max = arr[a];
                }
            }
            return max;
        }
        var ar = getMaxSum([5, 2, 99, 101, 67, 77]);
        console.log(ar);
```

### 2.6 arguments

```js
 // arguments 的使用  只有函数才有 arguments对象  而且是每个函数都内置好了这个arguments
        function fn() {
            // console.log(arguments); // 里面存储了所有传递过来的实参  arguments = [1,2,3]
            // console.log(arguments.length);
            // console.log(arguments[2]);
            // 我们可以按照数组的方式遍历arguments
            for (var i = 0; i < arguments.length; i++) {
                console.log(arguments[i]);

            }
        }
        fn(1, 2, 3);
        fn(1, 2, 3, 4, 5);
        // 伪数组 并不是真正意义上的数组
        // 1. 具有数组的 length 属性
        // 2. 按照索引的方式进行存储的
        // 3. 它没有真正数组的一些方法 pop()  push() 等等


 // 利用函数求任意个数的最大值
        function getMax() { // arguments = [1,2,3]
            var max = arguments[0];
            for (var i = 1; i < arguments.length; i++) {
                if (arguments[i] > max) {
                    max = arguments[i];
                }
            }
            return max;
        }
        console.log(getMax(1, 2, 3));
        console.log(getMax(1, 2, 3, 4, 5));
        console.log(getMax(11, 2, 34, 444, 5, 100));
```



## 3 案例

### 3.1 求两个数的最大值

```js
 // 两个数的最大值
        var num1 = +prompt('请输入第一个值');
        var num2 = +prompt('请输入第二个值');

        function getSum(num1, num2) {
            if (num1 > num2) {
                return num1;
            } else {
                return num2;
            }
        }
        var given = getSum(num1, num2);
        alert(given)

        // 三个数的最大值

        var num1 = +prompt('请输入1个数值');
        var num2 = +prompt('请输入2个数值');
        var num3 = +prompt('请输入3个数值');

        function getMax(arr) {

            var max = arr[0];
            for (var a = 1; a < arr.length; a++) {
                if (arr[a] > max) {
                    max = arr[a];
                }

            }
            return max;
        }
        var given = getMax([num1, num2, num3]);
        alert(given);
```

### 3.2 函数翻转数组

```js
var arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];

        function getNewArr(newArr) {
            var newArr = [];
            for (var a = arr.length - 1; a >= 0; a--) {
                newArr[newArr.length] = arr[a];
            }
            return newArr;
        }
        var re = getNewArr(newArr);
        console.log(re);
```

### 3.3 函数数组排序

```js
var arr = [2, 6, 1, 77, 52, 25, 7];

        function getArr(arr) {
            for (var a = 0; a < arr.length - 1; a++) {
                for (var b = 0; b < arr.length - a - 1; b++) {
                    if (arr[b] < arr[b + 1]) {
                        var temp = arr[b];
                        arr[b] = arr[b + 1];
                        arr[b + 1] = temp;
                    }
                }
            }
            return arr;
        }
        console.log(getArr(arr));
```

# 五 JS基础第五天

## 1 作用域

全局作用域：作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件。

局部作用域：作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域。

## 2 变量 

```js
 // 变量的作用域： 根据作用域的不同我们变量分为全局变量和局部变量
        // 1. 全局变量： 在全局作用域下的变量 在全局下都可以使用
        // 注意 如果在函数内部 没有声明直接赋值的变量也属于全局变量
        var num = 10; // num就是一个全局变量
        console.log(num);

        function fn() {
            console.log(num);

        }
        fn();
        // console.log(aru);

        // 2. 局部变量   在局部作用域下的变量   后者在函数内部的变量就是 局部变量
        // 注意： 函数的形参也可以看做是局部变量
        function fun(aru) {
            var num1 = 10; // num1就是局部变量 只能在函数内部使用
            num2 = 20;
        }
        fun();
        // console.log(num1);
        // console.log(num2);
        // 3. 从执行效率来看全局变量和局部变量
        // (1) 全局变量只有浏览器关闭的时候才会销毁，比较占内存资源
        // (2) 局部变量 当我们程序执行完毕就会销毁， 比较节约内存资源
```

## 3 作用域链

```js
  // 作用域链  ： 内部函数访问外部函数的变量，采取的是链式查找的方式来决定取那个值 这种结构我们称为作用域链   就近原则
        var num = 10;

        function fn() { // 外部函数
            var num = 20;

            function fun() { // 内部函数
                console.log(num);

            }
            fun();
        }
        fn();
```

## 4 预解析

```js
 // 1问  
        console.log(num);



        // 2问
        console.log(num); // undefined  坑 1
        var num = 10;
        // 相当于执行了以下代码
        // var num;
        // console.log(num);
        // num = 10;



        // 3问  
        function fn() {
            console.log(11);
        }
        fn();




        // 4问
        fun(); // 报错  坑2 
        var fun = function() {
                console.log(22);

            }
            // 函数表达式 调用必须写在函数表达式的下面
            // 相当于执行了以下代码
            // var fun;
            // fun();
            // fun = function() {
            //         console.log(22);

        //     }

        // 1. 我们js引擎运行js 分为两步：  预解析  代码执行
        // (1). 预解析 js引擎会把js 里面所有的 var  还有 function 提升到当前作用域的最前面
        // (2). 代码执行  按照代码书写的顺序从上往下执行
        // 2. 预解析分为 变量预解析（变量提升） 和 函数预解析（函数提升）
        // (1) 变量提升 就是把所有的变量声明提升到当前的作用域最前面  不提升赋值操作
        // (2) 函数提升 就是把所有的函数声明提升到当前作用域的最前面  不调用函数
```

## 5 对象

### 5.1 创建对象

```js
// 1.利用对象字面量创建对象 {}
        // var obj = {};  // 创建了一个空的对象 
        var obj = {
                uname: '张三疯',
                age: 18,
                sex: '男',
                sayHi: function() {
                    console.log('hi~');

                }
            }
            // (1) 里面的属性或者方法我们采取键值对的形式  键 属性名 ： 值  属性值 
            // (2) 多个属性或者方法中间用逗号隔开的
            // (3) 方法冒号后面跟的是一个匿名函数
            // 2. 使用对象
            // (1). 调用对象的属性 我们采取 对象名.属性名 . 我们理解为 的
        console.log(obj.uname);
        // (2). 调用属性还有一种方法 对象名['属性名']
        console.log(obj['age']);
        // (3) 调用对象的方法 sayHi   对象名.方法名() 千万别忘记添加小括号
        obj.sayHi();

        
```



```js
// 利用 new Object 创建对象
        var obj = new Object(); // 创建了一个空的对象
        obj.uname = '张三疯';
        obj.age = 18;
        obj.sex = '男';
        obj.sayHi = function() {
                console.log('hi~');

            }
            // (1) 我们是利用 等号 = 赋值的方法 添加对象的属性和方法
            // (2) 每个属性和方法之间用 分号结束
        console.log(obj.uname);
        console.log(obj['sex']);
        obj.sayHi();
```

```js
 // 利用构造函数创建对象
        // 我们需要创建四大天王的对象  相同的属性： 名字 年龄 性别  相同的方法： 唱歌
        // 构造函数的语法格式
        // function 构造函数名() {
        //     this.属性 = 值;
        //     this.方法 = function() {}
        // }
        // new 构造函数名();
        function Star(uname, age, sex) {
            this.name = uname;
            this.age = age;
            this.sex = sex;
            this.sing = function(sang) {
                console.log(sang);

            }
        }
        var ldh = new Star('刘德华', 18, '男'); // 调用函数返回的是一个对象
        // console.log(typeof ldh);
        console.log(ldh.name);
        console.log(ldh['sex']);
        ldh.sing('冰雨');
        var zxy = new Star('张学友', 19, '男');
        console.log(zxy.name);
        console.log(zxy.age);
        zxy.sing('李香兰')



        // 1. 构造函数名字首字母要大写
        // 2. 我们构造函数不需要return 就可以返回结果
        // 3. 我们调用构造函数 必须使用 new
        // 4. 我们只要new Star() 调用函数就创建一个对象 ldh  {}
        // 5. 我们的属性和方法前面必须添加 this


// 案例练习

        function Role(roleName, type, blood) {
            this.name = roleName;
            this.type = type;
            this.blood = blood;
            this.skill = function(ski) {
                console.log(ski);

            }
        }
        var lp = new Role('廉颇', '近战型', '150ml');
        console.log(lp.name);
        console.log(lp['type']);
        console.log(lp['blood']);
        lp.skill('飞毛腿');

        var zf = new Role('张飞', '远战型', '1500ml');
        console.log(zf.name, zf.type, zf.blood);
        lp.skill('扫堂腿');
```



### 5.2 new关键字的作用

1. 在构造函数代码开始执行之前，创建一个空对象；
2. 修改this的指向，把this指向创建出来的空对象；
3. 执行函数的代码；
4. 在函数完成之后，返回this---即创建出来的对象；
5. 这个对象的_proto_指向构造函数的原型。

### 5.3 this指向

```
1、普通函数中this指向的window
2、对象中的this指向的是当前这个对象
3、事件中this指向的是事件源
4、构造函数中的this指向的是new出来的那个实例对象
5、定时器中this指向的是window
备注：this始终指向的是函数的调用者
```

### 5.4 遍历对象

```js
// 遍历对象 
        var obj = {
                name: 'pink老师',
                age: 18,
                sex: '男',
                fn: function() {}
            }
            // console.log(obj.name);
            // console.log(obj.age);
            // console.log(obj.sex);
            // for in 遍历我们的对象
            // for (变量 in 对象) {

        // }
        for (var k in obj) {
            console.log(k); // k 变量 输出  得到的是 属性名
            console.log(obj[k]); // obj[k] 得到是 属性值

        }
        // 我们使用 for in 里面的变量 我们喜欢写 k  或者  key
```

# 六 JS基础第六天

## 1 内置对象

### 1.1 查文档

 MDN：https://developer.mozilla.org/zh-CN/

### 1.2  Math对象

Math 对象不是构造函数，它具有数学常数和函数的属性和方法。跟数学相关的运算（求绝对值，取整、最大值等）可以使用 Math 中的成员。

| 属性、方法名          | 功能                                         |
| --------------------- | -------------------------------------------- |
| Math.PI               | 圆周率                                       |
| Math.floor()          | 向下取整                                     |
| Math.ceil()           | 向上取整                                     |
| Math.round()          | 四舍五入版 就近取整   注意 -3.5   结果是  -3 |
| Math.abs()            | 绝对值                                       |
| Math.max()/Math.min() | 求最大和最小值                               |
| Math.random()         | 获取范围在[0,1)内的随机值                    |

```js
		// 绝对值
        console.log(Math.abs(1)); // 1
        console.log(Math.abs(-1)); // 1
        console.log(Math.abs('-1')); // 1

        // 向下取整
        console.log(Math.floor(1.1)); // 1
        console.log(Math.floor(1.6)); // 1

        // 向上取整
        console.log(Math.ceil(1.1)); // 2
        console.log(Math.ceil(1.6)); // 2

        // 四舍五入
        console.log(Math.round(1.5)); // 2
        console.log(Math.round(1.1)); //1

        // 随机值
        console.log(Math.random(1, 10));

        // 指定范围内的随机整数
        function getRandom(min, max) {
            return Math.floor(Math.random() * (max - min + 1)) + min;
        }
        var sum = getRandom(1, 10);
        console.log(sum);
        var arr = ['张三', '张三丰', '张三疯子', '李四', '李思思', 'pink老师'];
        console.log(arr[getRandom(0, arr.length - 1)]);
```

```js

// 猜数字
function getRandom(min, max) {
            return Math.floor(Math.random() * (max - min + 1)) + min;
        }
        var random = getRandom(1, 10);

        while (true) {
            var num = +prompt('请输入1-10之间的一个数');
            if (num > random) {
                alert('你猜大了');
            } else if (num < random) {
                alert('你猜小了');
            } else {
                alert('猜对了');
                break;
            }
        }
```

### 1.3 Date对象

Date 对象和 Math 对象不一样，Date是一个构造函数，所以使用时需要实例化后才能使用其中具体方法和属性。Date 实例用来处理日期和时间。

```js
		var date = new Date(); // 如果里面没有跟具体时间，则以系统时间为准
        console.log(date);

        var date1 = new Date(2019, 10, 1) // 数字型 返回的是11月 不是10月
        console.log(date1);

        var date2 = new Date('2019-10-1 8:8:8') // 字符串型
        console.log(date2);

        // 获取年月日

        var date = new Date();
        // console.log(date.getFullYear()); // 年
        // console.log(date.getMonth() + 1); // 月是01-11月，所以需要+1
        // console.log(date.getDate()); // 日
        // console.log(date.getDay()); // 星期几

        var year = date.getFullYear();
        var month = date.getMonth() + 1;
        var date1 = date.getDate();
        var arr = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
        var day = date.getDay();
        console.log(year + '年' + month + '月' + date1 + '日 ' + arr[day]);
```

```js
 // 获取毫秒
 // 实例化Date对象
var now = new Date();
// 1. 用于获取对象的原始值
console.log(date.valueOf())	
console.log(date.getTime())	
// 2. 简单写可以这么做
var now = + new Date();			
// 3. HTML5中提供的方法，有兼容性问题
var now = Date.now();
```

```js
// 倒计时案例

// 倒计时效果
        // 1.核心算法：输入的时间减去现在的时间就是剩余的时间，即倒计时 ，但是不能拿着时分秒相减，比如 05 分减去25分，结果会是负数的。
        // 2.用时间戳来做。用户输入时间总的毫秒数减去现在时间的总的毫秒数，得到的就是剩余时间的毫秒数。
        // 3.把剩余时间总的毫秒数转换为天、时、分、秒 （时间戳转换为时分秒）
        // 转换公式如下： 
        //  d = parseInt(总秒数/ 60/60 /24);    //  计算天数
        //  h = parseInt(总秒数/ 60/60 %24)   //   计算小时
        //  m = parseInt(总秒数 /60 %60 );     //   计算分数
        //  s = parseInt(总秒数%60);            //   计算当前秒数

        function countDown(time) {
            var nowTime = +new Date();
            var inputTime = +new Date(time);
            var times = (inputTime - nowTime) / 1000; // 1s = 1000ms 转换为秒
            var d = parseInt(times / 60 / 60 / 24); // 天
            d = d < 10 ? '0' + d : d;
            var h = parseInt(times / 60 / 60 % 24) // 小时
            h = h < 10 ? '0' + h : h;
            var m = parseInt(times / 60 % 60); // 分
            m = m < 10 ? '0' + m : m;
            var s = parseInt(times % 60); // 秒
            s = s < 10 ? '0' + s : s;
            return d + '天' + h + '时' + m + '分' + s + '秒';
        }
        console.log(countDown('2019-5-17 08:00:00'));
        var date = new Date();
        console.log(date);
```

### 1.4 数组对象

#### 1 创建数组的两种方式

①字面量方式

```js
var arr = [1,"test",true];
```

②new Array()

```js
var arr = new Array();
```

#### 2 检验是否为数组

```js
var arr = [];
        var obj = {};

        // 方法一  (1) instanceof  运算符 它可以用来检测是否为数组
        console.log(arr instanceof Array); // ture
        console.log(obj instanceof Array); // false

        // 方法二 Array.isArray(参数);  H5新增的方法  ie9以上版本支持
        console.log(Array.isArray(arr));
        console.log(Array.isArray(obj));
```

#### 3 添加删除数组元素的方法

```js
 // 1 、push()数组最后添加一个数组元素
        var arr = [];
        arr.push(444); // [444]
        arr.push(666); // [444,666]
        console.log(arr);

        // 2、unshift()数组的开头，添加一个或者多个元素
        var arr1 = [99, 88];
        arr1.unshift(55, 66, 44);
        console.log(arr1);

        // 3、pop()删除数组最后一个元素
        var arr2 = [1, 2, 3, 4]
        arr2.pop()
        console.log(arr2);

        // 4、shift()可以删除数组第一个元素
        var arr3 = [1, 2, 5, 9]
        arr3.shift()
        console.log(arr3);

	    // 5、splice(开始删除位置的索引，要删除几项，是否补位)
		var arr4 = [1, 2, 3, 4]
         arr4.splice(3, 1, 9999)
		console.log(arr4)
```

#### 4 数组排序

```js
	   // 翻转数组
        var arr1 = ['小明', '小花', '小兰', '侠侣']
        arr1.reverse()
        console.log(arr1);

        //数组排序  冒泡排序
        var arr2 = [1, 5, 8, 4, 2, 3]
        arr2.sort(function(a, b) {
            return a - b;

        })
        console.log(arr2);
```

#### 5 数组转化为字符串、数组去重

```js
// 数组去重 ['c', 'a', 'z', 'a', 'x', 'a', 'x', 'c', 'b'] 要求去除数组中重复的元素。
        // 1.目标： 把旧数组里面不重复的元素选取出来放到新数组中， 重复的元素只保留一个， 放到新数组中去重。
        // 2.核心算法： 我们遍历旧数组， 然后拿着旧数组元素去查询新数组， 如果该元素在新数组里面没有出现过， 我们就添加， 否则不添加。
        // 3.我们怎么知道该元素没有存在？ 利用 新数组.indexOf(数组元素) 如果返回时 - 1 就说明 新数组里面没有改元素
        // 封装一个 去重的函数 unique 独一无二的 
        function unique() {
            var arr = ['c', 'a', 'z', 'a', 'x', 'a', 'x', 'c', 'b'];
            var newArr = [];
            for (var i = 0; i < arr.length; i++) {
                if (newArr.indexOf(arr[i]) == -1) { // newArr.indexOf(arr[i])  == -1  说明newArr里面没有这个数组元素 如果没有这个数组元素就添加到里面
                    newArr.push(arr[i]);
                }
            }
            console.log(newArr);
        }
        unique()

        // 数组转换为字符串

        var arr2 = ['昭君', '西施', '貂蝉', '杨玉环'];
        console.log(arr2.join()); // 昭君,西施,貂蝉,杨玉环
        console.log(arr2.join('-')); // 昭君-西施-貂蝉-杨玉环
        console.log(arr2.join('$')); // 昭君$西施$貂蝉$杨玉环
        console.log(arr2.join('*')); // 昭君*西施*貂蝉*杨玉环
```

### 1.5 字符串对象

#### 1 根据位置返回字符

```js
// 1. charAt(index) 根据位置返回字符

        var str = 'jessica';
        console.log(str.charAt(3));
        // 遍历所有字符

        for (var i = 0; i < str.length; i++) {
            console.log(str.charAt(i));
        }

        //  2、charCodeAt(index)  返回相应索引号的字符ASCII值 目的： 判断用户按下了那个键 

        console.log(str.charCodeAt(3)); // 105

        // 3、str[index] H5 新增的
        console.log(str[1]); //e
```

#### 2 字符串的操作方法

```js
// 字符串操作方法
        // 1. concat('字符串1','字符串2'....)  合并字符串

        var str = 'abc';
        console.log(str.concat('red'));
        // 1.1方法
        var str1 = [11, 22]
        var str2 = [33, 44]
        var ss = str1.concat(str2)
        console.log(ss);

        // 2. substr('截取的起始位置', '截取几个字符');
        var str3 = '好好学习，天天向上'
        console.log(str3.substr(2, 2)); // 学习  // 第一个2 是索引号的2 从第几个开始  第二个2 是取几个字符

        // 3. 替换字符 replace('被替换的字符', '替换为的字符')  它只会替换第一个字符

        var str4 = 'abadaf'
        console.log(str4.replace('a', '@'));

        //4.有一个字符串 'abcoefoxyozzopp'  要求把里面所有的 o 替换为 *
        var str5 = 'abcoefoxyozzopp';
        for (var i = 0; i < str5.length; i++) {
            if (str5.indexOf('o') !== -1) {
                str5 = str5.replace('o', '*');
            }
        }
        console.log(str5);

        // 字符转换为数组 split('分隔符')   前面我们学过 join 把数组转换为字符串
        var str6 = '小红, 小明, 小兰';
        console.log(str6.split(','));
        var str7 = '小红&小明&小兰';
        console.log(str7.split('&'));
```

## 2 简单数字类型和复杂数字类型

- 简单类型**（**基本数据类型**、**值类型**）：在存储时变量中存储的是值本身，包括string ，number，boolean，undefined，null。
- 复杂数据类型（引用类型）：在存储时变量中存储的仅仅是地址（引用），通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等。

## 3 案例

```js
	// 1、在控制台输出 1到100之间 所有能被5整除的数的和

        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            if (i % 5 !== 0) {
                continue;
            }
            sum = sum + i;
        }
        console.log(sum);

        // 2、请将1到100之间所有能被3整除的数字添加到新数组arr中，并打印到控制台

        var arr = [];
        for (var i = 1; i <= 100; i++) {
            if (i % 3 === 0) {
                arr[arr.length] = i;
            }
        }
        console.log(arr);

        // 3、打印九九乘法表

        var num = '';
        for (var i = 1; i < 10; i++) {
            for (var j = 1; j <= i; j++) {
                num = num + i + '*' + j + '=' + j * i;
                num = num + '\t';
            }
            num = num + '\n';
        }
        console.log(num);

        // 4、已知数组 arr = [1,9,3,7,5] ,使用程序计算出该数组的最大值，封装成函数


        function getMax() {
            var arr = [1, 9, 3, 7, 5];
            var max = arr[0];
            for (var i = 1; i < arr.length; i++) {
                if (arr[i] > max) {
                    max = arr[i];
                }
            }
            console.log(max);
        }
        getMax()

        // 5、封装一个对数组元素进行冒泡排序的函数（从大到小） 

        function getArr(arr) {
            for (var i = 0; i < arr.length; i++) {
                for (var j = 0; j < arr.length - i; j++) {
                    if (arr[j] < arr[j + 1]) {
                        var temp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = temp;
                    }
                }
            }
            return arr;
        }
        var re = getArr([1, 9, 3, 7, 5]);
        console.log(re);

        // 6、 编写一个函数， 将如下字符串 'get-element-by-id'

        // 修改为驼峰表示法 'getElementById'
        // 方法一
        var str = 'get-element-by-id';

        function combo(str) {
            var parts = str.split('-');
            for (var i = 1, len = parts.length; i < len; i++) {
                parts[i] = parts[i].charAt(0).toUpperCase() + parts[i].substring(1);
            }
            return parts.join('');
        }
        alert(combo(str));

        // 方法二

        function fn() {
            var str = 'get-element-by-id';
            var tmpArr = str.split('-'); // ["get", "element", "by", "id"]
            var newStr = tmpArr[0]; // "get"
            for (var i = i; i < tmpArr.length; i++) {
                newStr += tmpArr[i][0].toUpperCase() + tmpArr[i].substr(1);

            }
            return newStr
        }
        fn()
```

