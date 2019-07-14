html与css不是编程。
js：编程语言。  通过自己的逻辑思维实现特定的功能。
00010--hello
#javascript是什么？
	一种编程的脚本语言！ 用于实现页面的动态效果；
#javascript 历史背景：
	sun公司（java）；
	网景公司与sun公司---布兰登艾奇  7-10天  1995年   javscript（C语言   java） 
	原创之处并不优秀  优秀之处并非原创！！！
#javascript早起的目的：
	表单验证：  用户提交返回内容    当用户输入有误立刻弹出错误信息。
#javascript现在的价值：
	浏览器与服务器的动态交互
	实现网页的动态效果
	小游戏
	绘画  地图  
	基于node实现服务器开发。
#javascript特点：
	1.直译型  浏览器认识js语言  不需要提前翻译  直接解析   java 浏览器先解析（浏览器认识的语言）
	js:var num = 10;
	java:int num = 5;
	2.弱类型语言：指定什么类型就是什么变量
	var num = 10  var num = "hello"
	3.基于对象式开发；
	4.跨平台（所有的浏览器都认识js）；
#javascript组成：
	ECMAscript：欧洲协会组织  研发一些基本的语法  
	bom：  用户操作浏览器
	dom： 操作文档；

#js第一天：

	js的书写规范：
		1.内部  
		2.外部  如果引用外部的js  script标签内部不要写代码
	html:    <!-- -->	
	css: /* */
	js: /* */ 多行    //单行
##js的几种输出方式：
	1.alert: 弹出警示框
	2.console.log("")  控制面板！！！！
	3.document.write("1234"); 文档打印！！！
	4.prompt("请输入",123); 弹出输入框   参数1：提示信息  参数2： 默认值
##变量：
	var num = 10;
	声明一个变量名叫num 值是10；
		注意： 1.即声明又给值  结果是当前的值 2.只声明不给值：undefined 3,没有声明直接给值  浏览器自动加上 4.既没有声明又没有给值 结果报错；
		一个变量只能存储一个值！！
	声明变量的几种方式：
		1.var num = 10; var num1 = 20;
		2.var num=10,num1=20;
		3.var num,num1;
		 num=10;
		 num=20;
	变量的命名规则：
		1.由数字  字母  下划线  $符号 组成;
		2.不能以数字开头 
		3.不能使用 关键字 保留字
		4.见名知意
		5遵循驼峰命名法  uName   userSchool;
		6.变量名不能超过255个字符；
##js的数据类型：
	1.基本数据类型
		1).数值型（十进制）
			0-所有的自然数   小数  负数  NaN:不是一个数字
		2)字符串
			只要加引号都属于字符串   特殊字符 只适用于console.log()   \n换行   "un'de'fined"  'und"ef"ined'
			str.length:  访问字符串的长度
			str[索引|下标] 访问对应的每一个字符  索引从0开始
			只要与字符串相加 就会相连！！！
		3.布尔型
			true|false
			如果参与运算： true=1   false=0
		4.undefined： 只声明没给值   

		5.null（对象）： 一般清空内存；
	
		typeof 检测数据类型；
		isNaN判断是否是数字  如果是数字返回false  不是数字返回true   "isNaN会默认尝试把内容转换成数字"!!
	2.数据类型的转换：
		1.转换为字符型：
			强制类型转化：
				num.toString()
				String(num)
			隐式类型转换：
				10+""	
		2.转换为数值类型：
			强制类型转化：
				parseInt():
					1.取整。
				parseFloat();
					1.保留小数；
				Number()
					1.取整--保留小数   
				三者的区别：
					parseInt  结果是整数  字母在前  NaN  字母在后 干掉字母（保留整数）！
					parseFloat 结果是小数  字母在前  NaN  字母在后 干掉字母（保留小数）！
					Number  只要有字母结果NaN
			隐式类型转换：
				1. 直接加 + 号
				2.  -0  /1 *1
		3.转换为布尔类型：
			强制类型转换：
				Boolean()
			隐式类型转换：	
				!!  双重否定等于肯定
			转换成false的情况：
				0  undefined  null  NaN  false  ""  都是false；
js第三天：
	for(初始变量;循环的终止条件;循环的增量){
		执行的代码块
	}   
	for循环 与 while循环换
		for循环一般用于知道循环次数；
		while循环   不知道循环次数；
	while 与 do..while区别：
		while:先判断在执行
		do..while:先执行在判断
	continue  break 区别：
		continue：跳出当前循环 继续下一次循环
		break: 跳出整个循环
js第四天：
	什么是数组:
		一组数据数据的集合
	为什么使用数组：
		方便对数据的统一管理
		var arr = ["张三","李四"];
		var a = "张三";
		var b = "李四";
	数组的使用：
		1.创建数组：
			1.创建空数组  var arr = [];
			2.创建空数组  var arr = new Array();
			3.创建有元素的数组var arr = [1,2,3,4,5]
			4.创建有元素的数组var arr = new Array(1,2,3,4,5)
			[]与new Array 区别： 
				当只有一个数据(数字) new Array代表数组的长度   [] 代表一个数据
		2.数组的使用:
			1.获取元素：
				1.下标（索引） 默认的索引从0开始  数组名[索引值]   当访问没有定义内容的数组  结果是undefined
				2.length数组的长度  长度从1开始
			2.数组里面嵌套数组：二维数组
		3.数组的改变：
			1.数组可以动态改变
			2.清空数组  数组名.length = 0  数组名 = null
			var arr = [1,2,3]
		4.数组可以存什么:
			数组可以存储任意数据类型的元素
			一般数组存储一种数据类型
		5.数组的方法:
			push: 数组.push(元素) 向末尾添加元素
			pop:  数组.pop()删除数组末尾的元素
			unshift： 数组.unshift(元素) 数组的前面添加内容
			shift：  数组.shift()删除数组的第一个元素
	什么是函数：
		可重复使用的代码块
	为什么使用函数：
		1.减少代码量
		2.使代码有模块化
	函数的使用： 函数不调用自己不执行；
		定义函数：
			1. function fn(){
				执行的代码块
       		 }
			fn是函数名;
			2.var fn = function(){
				执行的代码块
       		}
		函数的调用：
			函数名();
	函数的参数：
		形参：形式上的参数   定义函数时候的参数  本质是变量
		实参：实际上的参数   调用函数时候的参数  本质是数据
	参数个数的问题
		1.当实参大于形参：多余的实参忽略不计
		2.当形参大于实参: 多余的形参赋值给undefined
		总结：实参与形参要相匹配；
	return：返回值
		一个函数可以有返回值 也可以没有
		1.如果只是单纯的打印（看到值） 可以不加return
		2.当用函数实现某种特定的功能 要加return
		3.当遇见return  直接退出函数体  下面不在执行
		4.一个函数只有一个return；
		5.不加return  默认返回undefined;
js第五天：
	arguments: 伪数组：具有数据的一些属性 但是也不具有数组的一些方法 
		  arguments:实参的对象 只要创建函数默认就有arguments 	
		  一般 形参多少  实参多少   arguments用的不多！！！

	函数以参数的形式传递----回调函数
	作用域：
		全局作用域：在函数外部都是全部作用域
		局部作用域： 在函数内部都是局部作用域

		全局变量： 在任何地方都可以访问
		局部变量： 只能在当前作用域下访问
		总结 局部可以访问全局    全局不可以访问局部  
	作用域链的基本原理：
		当调用函数---会把函数推送到执行栈（局部作用域）----全局作用域与函数的链式称为作用域链。 0级作用域链----1级作用域链

	预解析：(提升（变量名，函数）当前作用域的最前面！！)
		当浏览器加载的时候 会有提前预解析的过程；
			提升：  var num = 10;    var num;	
			提升:   function fn(){}   function fn(){}
			注意：
					1.在函数内部 变量名与形参重名以形参为主！！
					2.函数内部不加var关键字是全部变量（不能与形参重名）
					3.函数定义当前作用域   与函数调用没有关系（不会改变当前函数的作用域）;
	对象：  万物皆对象！！！！
		1.键值对的集合。
		2.功能集与数据集的集合
			数据集的描述： 属性:属性值
			功能集的描述： 函数名：函数
		普通函数与对象的函数：
			对象的函数前面加对象
		对象的获取：
			对象.属性名
			对象["属性名"]
			obj.方法()
		对象的几种创建方式：
		1.创建空对象： 在动态添加值
			 var obj = {};
			obj.name = "kf";
			obj.age = 18;
			obj.sex = "nan";
		2.创建有内容的对象
			var obj = {
				name:"kf",
				age:"18",
				sex:"nan"
			}
		3.创建空对象：
			var obj = new Object();
			obj.name = "kf";
			obj.age = 18
		4.创建有内容的对象：
			var obj = new Object({
				name:"kf",
				age:18
			})	
		对象的封装：
			工厂模式：
			function person(name, age, sex) {
				//var obj = {};
				var obj = new Object()
				obj.name = name;
				obj.age = age;
				obj.sex = sex;
				return obj;
			}
			构造函数：
			function Person(name,age,sex){
				this.name = name;
				this.age = age;
				this.sex = sex 
			}
			var per = new Person("tongtong",30,"男")
			var per = person("jujie",50,"男");
		new的执行过程：
			1.创建空对象（创建内存地址）
			2.改变this指向当前对象
			3.执行构造函数的代码
			4.返回this；
		对象的遍历:
			for(var key in 对象){
				obj[key]
			}
		<!-- 了解：只要是对象就有加密的过程！
			哈希值： 哈希算法（加密）
				！！属性对应属性值 ----通过哈希-----通过加密过后的密码对应着不同的属性值 -->


	面向过程：
		 举行晚会：
            1.找演员--->2.找吃的--->3.灯光摄影--->4.抽奖活动
	面向对象：
		举行晚会：
            1.找演员--->2.找吃的--->3.灯光摄影--->4.抽奖活动

js第六天：
	数学对象：
		1.Math.PI 
		2.Math.max(1,3,4)
		3.Math.min()
		4.random()
		5.floor()
		6.ceil
	日期对象：
		构造函数：  
			1.var date = new Date();
			2.可以添加参数获取的是参数对应的日期
			3.不添加参数 获取的是当前日期
		方法：
			1.获取年： getFullYear()
			2.获取月： getMonth() 获取月要加1
			3.获取日期：getDate()
			4.获取星期：getDay 星期日是0 
			5.获取时： getHours()
			6.获取分：getMinutes();
			7.获取秒：getSeconds();
		获取毫秒值：
			获取的距离1970年1月1日
			1.获取的方式
				1.date.valueOf()
				2.date.getTime()
				3.+new Date()
				4.h5新增  Date.now()
			2.typeof判断
				基本数据类型
			3.判断对象（数组）
				1.instanceof  arr instanceof Array;
				2.Array.isArray(arr);
			4.数组的方法：
				push: 数组.push(元素) 向末尾添加元素
				pop:  数组.pop()删除数组末尾的元素
				unshift： 数组.unshift(元素) 数组的前面添加内容
				shift：  数组.shift()删除数组的第一个元素
				reverse():翻转数组
				arr.sort(function (a, b) { 排序
					return a - b  升序
					return b - a  降序
				})
				indexOf():查找元素  没有找到对应的元素  返回-1  找到返回对应的索引;
				join() 参数： 把数组以参数的形式分隔  如果不传默认是逗号分隔;
				concat:合并数组
				slice: 不修改原数组 截取 （开始索引,结束索引）  不包含结束索引  如果只传递一个参数  从当前参数截取到最后。
				splice:修改原数组  截取 （开始索引,截取的长度,要替换的元素） 
		基本包装类型：   万物皆对象！！！！ 
			基本数据类型 通过包装  转化成复杂数据类型；
			1. 后台的调用  方便程序员使用一些属性和方法----基本包装类型
				计算机默认：
				创建对象
   					 var str = "hello";
					var str1 = new String("hello");
					把变量给当前变量
					str = str1;
					内存释放 销毁
					str1 = null
				基本包装类型与复杂数据类型的区别：
					1.都可以使用字符串的一些方法与属性
					2.基本包装类型创建完之后立刻销毁。
			1.字符串：
				面试题： 如何优化代码的性能：
				字符串的不可变； 用数组解决
					字符串：重新开辟内存空间  原来的内容不会销毁
					数组： 不会重新开辟内存空间  会把原来的覆盖。
				    var str = "";
					var arr = [];
					for (var i = 0; i < 100; i++) {
						arr.push(i)
					}
					console.log(arr.join(""));
				indexOf:查找元素  
					indexOf("元素",开始查找的索引)	 找到返回索引  找不到返回-1
				str.charAt(索引)：查找对应的元素
				str[0]	查找对应的元素
				concat拼接字符串
				toUpperCase:转化大写
				toLowerCase转化小写
				substring（2,5） 字符串的截取
				split("-") 转化成数组
	基本数据类型与复杂数据类型的存储方式：
		基本数据类型存储在栈里面  本质是真是的数据；
		复杂数据类型存储在对里面   对里面本质真是的数据   栈里面存的是地址；

API第一天：
    1.API：应用程序接口   arr.push()   
    DOM:页面上所有的动态效果;

    获取元素：
    1.通过id名获取：
         // 获取元素  通过id的形式获取   元素    通过id的形式获取 只能通过document获取
          // var box = document.getElementById("box");
    2.通过标签名的形式获取
          // // 获取元素   通过标签名获取   伪数组（集合）   不管页面有几个元素   获取的都是伪数组 
         // var li = document.getElementsByTagName("li");
    3.通过class的形式获取：
          // // 获取元素  通过class的形式获取  伪数组（集合） 
         // var one = document.getElementsByClassName("one");
    4.h5新增的选择器：
        var box = document.querySelector("div");   .class   #id   标签名  获取一个元素;
        var box = document.querySelectorAll("#box")   .class   #id   标签名 获取所有的元素 伪数组;
    5.获取body元素：document.body;
    5.获取html元素： document.documentElement;

    innerHTML与innerText 都是设置 或者 获取元素内容的
        获取的区别：
            innerHTML：会获取空格  标签  文本
            innerText: 不会获取空格  标签  只会获取文本
        设置的区别：
            innerHTML：会解析标签
            innerText:不会解析标签；
    this：事件下面的this
        事件的调用者  事件的执行者。
            checked:true:默认选中项
            selected：true: 默认选中项
            disabled:true; 禁用
    className:操作类名；
    style:本质是行内样式；
    自定义属性： 自己定义的属性；
        获取 元素.getAttribute("属性名");
        设置: 元素.setAttribute("属性名","属性值");
        删除：元素.removeAttribute("属性名");
    h5新增的自定义属性：
        定义： data-开头  data-name
        获取： 
            1.  ele.dataset.name;
            2.  ele.dataset["name"];
        节点：
            元素节点  文本节点  属性节点
            元素节点：
                1.parentnode  父节点
                2.children  子元素
                3.firstELementChild:第一个子元素
                4.lastELementChild:最后一个子元素
                5.appendChild()
                6.insertBefore()
                7.cloneNode();
                8.createElement();
        克隆节点:  cloneNode(true|false)   box.cloneNode(false)
                 true: 代表深度克隆   会克隆里面的子元素
                 false：浅度克隆   只克隆当前标签
        创建元素:
            1.createElement("p");
            2.document.write("<p></p>");
            3.innerHTML = "<p></p>";
        #与（javascript:;）=（javascript:volid(0);）区别
             #会刷新页面  阻止页面跳转                       
             javascript:;  阻止页面跳转 
        事件的几种方式：
            1. <button onclick="fn(5)">点击</button>   
                 function fn(a) {
                   alert(a)
                }
            2. btn.onclick = function () {
                 alert(1)
            }
            3.btn.addEventListener("click", function () {
                alert(1)
            })
        清空事件的几种方式：
            1.  btn.onclick = function () {
                    alert(1);
                    btn.onclick = null;
                }
            2.btn.addEventListener("click", fn)
                function fn() {
                    alert(1);
                    btn.removeEventListener("click", fn)
                }
        事件流三个阶段   捕获  目标  冒泡
            捕获：  document--->html---body--->父元素--->目标元素；
            冒泡：  目标元素--->父元素--->body--->html--->docuemnt
            注意：
                当处于目标阶段的时候 捕获与冒泡谁先定义先执行谁！！
                任何事件都有捕获状态！！！
                事件流与位置没有关系  只要是嵌套都会依次发生事件
        事件对象（事件源参数e）

        target: 点击了谁(最里层的元素)；
        this: 绑定的事件
        阻止浏览器默认行为：
            1.  e.preventDefault();
            2.  return false;
        阻止事件冒泡：
             e.stopPropagation()；
        事件冒泡的应用场景---事件委托；
            给外层的元素绑定事件  通过e.target找到目标元素 在通过冒泡触发事件---事件委托
        事件委托的好处：
            减少内存空间
            提高效率  提升浏览器的加载速度！
            
    keydown:按下键盘 没有松开时候一直触发事件
    keyup： 弹起键盘时候触发；

    bom加载事件：
        1.load   window.onload = function(){}    等到页面元素，外部的js，图片和引用其他的资源绘制完毕再加载事件。
        2.DOMContentLoaded： 等到页面元素绘制完毕加会加载事件。
        3.resize：当窗口发生变化的时候触发事件;   
    延时器： 只执行一次 当前函数里的内容
        setTimeout(function(){

        },毫秒)
    清除延时器的方式：
        1.clearTimeout(timer)

    定时器： 重复执行 当前函数里的内容
        setInterval(function () {
          console.log(1)
        },毫秒数)

   this指向：
        this当调用时候确定this指向  当定义时候不能确定this指向！！  
            1.普通函数调用-------指向的是window（永远）;
            2.方法调用-----当前调用的对象   事件----当前调用的对象
            3.构造函数调用：高级回来！！！！!   call   apply   bind();
            4. setInterval(function () {
                 console.log(this)  //window
                },毫秒数)
        
    javascript单线程： 同一时间只能做一件事  上做完之后再继续执行下一件事
        同步：做一件事  造成性能问题；
        异步：做多个事  当执行主线程的内容   定时器放在任务队列里面 
        javascript运行机制：
            1.先执行主线程里的代码  
            2.当发现 定时器  会把定时器 放到任务对列里面去执行
            3.继续向下执行等主线程的所有代码执行完毕之后再去执行任务队列里的代码
            4.循环去任务队列里面去执行代码     （事件循环）
            5.执行完之后把任务队列清空；
        放到任务队里的东西：
            定时器   延时器  ajax  事件  es6---promise
        setInterval  setTimeout   0  误差--（0.4-10s）
    location对象：
        属性： href：设置或者获取地址栏信息路径
              search： 获取地址栏参数 ?name=kf&age=18
              pathname:返回路径  
              host:主机名
              port：端口号；
 
       

    立即执行函数：
        (function(){
            var num = 10
        })()
        目的：创建一个封闭的区域。避免变量的污染
       // var num = 10;
        function fn(){
            var num = 10
          
        }
        fn()
        垃圾回收机制：
            全局作用域下的变量  不会销毁；
            局部作用域下的变量  当关闭浏览器立刻销毁。
    坐标系列：
    3组大小位置相关的属性：
    1.offset:
        1.offsetWidth: 获取当前元素的宽度 （包含  width + padding + border）
        2.offsetHeight：获取当前元素的高度 （包含  width + padding + border）
        3.offsetLeft: 获取当前元素距离带有定位父元素的坐标
        4.offsetTop: 获取当前元素距离带有定位父元素的坐标
        5.offsetParent：获取带有定位的最近父元素
    offset与style
        offset: 获取的是内部样式  不带单位    获取元素位置
        style:获取行内样式   带单位  不包含 padding  及border  设置元素位置
    2.client：
        clientLeft: 获取的是边框的宽度
        clienttop: 获取的是边框的宽度
        clientWidth：获取的是内容的宽度  width + padding 不包含边框
        clientHeight：获取的是内容的高度  width + padding 不包含边框
    3.scroll
        scrollWidth： 内容的大小（包含padding和未显示的内容） 不包含滚动条
        scrollHeight： 内容的大小（包含padding和未显示的内容）不包含滚动条
        scrollLeft: 内容滚动出去的大小
        scrollTop: 内容滚动出去的大小




        mouseenter-----mouseLeave:不会触发事件冒泡；
        mouseover----mouseout:会触发事件冒泡


    touches:是指当前屏幕上的所有手指对象
    targetTouches：当前元素上的手指对象
    changedTouches：当前屏幕上变换的手指对象
    touches与targetTouches 测试中都一样

    screenX:是指手指的触摸点相对于屏幕的坐标
    screenY:是指手指的触摸点相对于屏幕的坐标

    clientX:当前视口的距离
    clientY：当前视口的距离

    pageX：相对于页面的距离
    pageY：相对于页面的距离

    classList:
        classList.add()增加类名  不会覆盖之前的一次只能添加一个！
        classList.item(索引) 获取类名  
        classList.remove() 移除类名
        classList.toggle() 切换  如有就删除  否则添加
        classList.contains(); 判断是否有该类名  有返回true  否则false
移动端click300毫秒延迟：
    要判断当前用户是双击 还是长按；
    本地存储：h5新增的；
    本质：存储用户的一些数据   方便使用操作！
    sessionStorage
        1.存储
            window.sessionStorage.setItem("属性名","属性值")
        2.获取
            window.sessionStorage.getItem("属性名");
        3.删除
            window.sessionStorage.removeItem("user");
        4.删除所有
            window.sessionStorage.clear()
    localStorage
         1.存储
            window.localStorage.setItem("属性名","属性值")
        2.获取
            window.localStorage.getItem("属性名");
        3.删除
            window.localStorage.removeItem("user");
        4.删除所有
            window.localStorage.clear();
        
        两者的区别!!!!：
            存储大小：
                sessionStorage 存储大小 5mb
                localStorage  存储大小 20mb
            共享信息：
                sessionStorage（不同的页面没有办法共享信息！ 存储在当前页面的内存）
                localStorage （不同的页面可以共享信息！本地内存）
            声明周期：
                sessionStorage  当关闭页面数据清除
                localStorage  永久存储
            共性：
                1.都可以存储数据
                2.只存储浏览器内存  不与服务器打交道   Cookies与服务器打交道

jq特点：
    1.隐式迭代
    2.链式编程
    当操作是设置型元素：可以一直链式编程
    当操作是获取型元素：不可以一直链式编程（断链）
1.jq的入口函数
    1.$(function(){

    });
    2.$(document).ready(function(){
        
    });
    3.jQuery(function(){

    });
2.dom与就jq互转：
    dom对象无法使用jq对象里的方法；
    jq对象无法使用dom对象的属性和方法；
    1.dom对象转jq对象：
        $("div")
        $(div)
    2.jq转dom对象：
        $("div")[0]
    3.jq转dom对象$("div").get(0)

3.jq选择器：
    id选择器： $("#id")  获取指定的id元素
    全选选择器： $("*") 获取所有
    类选择器：  $(".class") 获取指定的class选择器
    标签选择器：  $("div) 获取同一类的所有元素
    并集选择器： $("div,p,li")
    后代选择器： $("div li")
    交集选择器： $("div.current")
    子代选择器： $("div>li")
4.隐式迭代：
    遍历内部的dom元素的过程叫做隐式迭代
5.筛选选择器：
    $("li:first") 获取第一个li
    $("li:last") 获取最后一个li
    $("div:eq(2)") 获取索引为2的元素
    $("div:odd") 奇数
    $("div:even") 偶数
6.方法：
    parent()  $("li").parent() 查找父元素
    children(“li”) 最近的儿子
    find("li") 后代选择器
    siblings() 兄弟选择器
    nextAll() 查找当前元素之后的所有同辈元素
    prevAll() 查找当前元素之后的所有同辈元素
    hasClass() 查找当前类名
    eq(index)索引
    addClass（）增加类名 
jq的链式编程：
    获取型：布局有链式编程
    设置型：具有链式编程
jq的动画方法：


第一组动画：
    hide() 隐藏
    show() 显示
    两者可以写参数 可以写数字类型  第二个参数代表回调函数
    1.数字类型1000表示1秒
第二组动画：
    slideUp上拉
    slideDown下拉
    参数同上
第三组动画：
    fadeIn 淡入
    fadeOut 淡出
    fadeToggle切换
    fadeTo("")  不用
    .end() 结束当前的this 指回原来的this
自定义动画：
    animate：
        参数1：对象 ----运动的代码
        参数2：运动事件
        参数3：运动曲线
        参数4：动画执行完毕所要执行的代码
    
 



jq第二天：
    属性的操作：
        prop：获取的是元素固有的属性  获取自定义属性结果是undefined
        attr：获取的是自定义属性 attr 可以获取自定义属性同时可以获取固有属性
        data:本质生成在缓存机制里面  不会修改原来的属性 只会临时存储；
        removeAttr()移除属性   
    内容的文本值：
        html() 获取空格 标签 文本内容  设置会解析标签  innerHTML 
        text() 获取文本内容  设置不会解析标签  innerText
    jq遍历元素的方式：
        $("ele").each(function(索引,dom元素){

        })
        遍历对象  数组：
        $.each(对象,function(index,ele){

        })
    创建  添加  删除元素
    var li = $("<li>123</li>");
    在当前内容的后面添加元素
    $("div").append(li);
    添加到某个元素
    li.appendTo($("div"))
     在当前内容的前面添加元素
    $("div").prepend(li)；
    添加到当前内容的前面添加元素
    li.prependTo($("div"))
    同级元素前面：
    $("div").before(li)
    同级元素的后面
    $("div").after(li)
    删除元素：
    $("div").remove()
    父元素.empty()
    父元素.html("")  注意：如果子元素有事件只是清除内容  事件还在内存；

jq里面的尺寸：
    width()  height()  只包含宽度高度
    innnerwidth()  innnerheight()  包含padding
    outerwidth()  outheight()包含padding+border
    outwidth(true) 包含padding  border  margin
jq里面的位置：
    offset()获取元素距离屏幕的距离 offset().top  
    position()获取距离父元素有定位的距离  
    scrollTop():获取页面卷曲出去的距离
    scrollLeft():获取页面卷曲出去的距离

jq第三天：
    on注册事件：
        1.事件委托
        2.动态创建的元素无法有事件  所以需要通过事件绑定 只要是通过动态创建出来的元素 那么必须通过on绑定事件
        3.事件解绑   $("div").off()  解绑当前元素的所有事件   $("div").off(“click”)
        4.委托解除绑定   $("div").off("click","li");
         $("#btn1").click()
		$("#btn1").trigger("click")
		$("#btn1").triggerHandler("click")
		trigger与triggerHandler区别：
			trigger：会触发事件冒泡  会触发浏览器的默认行为
			triggerHandler：不会触发事件冒泡  不会触发浏览器的默认行为;
        jq阻止事件冒泡
            1.e.stopPropagation()
            2. return false;在jq里面可以阻止事件冒泡； 在dom不能阻止事件冒泡；
       多库共存： 
        1.var 变量 = jQuery.noConflict()   本质把$赋值给变量
        2.jQuery("div");
        extend() 对象与对象之间的拷贝
         浅拷贝：
            属性拷贝的是值  方法（对象拷贝的地址） 
        深拷贝：
             属性拷贝的是值  方法（对象拷贝的值） 
         $.extend(true, obj, target);  
            参数1：深拷贝|浅拷贝
            参数2：拷贝的对象
            参数3：拷贝的目标对象
            对象里面有相同的属性（方法） 会把原来的覆盖掉
        $.fn---jq方法的顶级对象
    懒加载：
        对于页面有很多静态资源，为了节省用户流量和提高页面性能，可以在用户浏览到当前资源的时候
        在对资源进行请求加载。

        原理：简单理解： 当访问一个页面的时候 先把img元素或其他元素的背景图片路径替换一张图片（这样只请求一次）
        只有当图片出现在可视区域内时，才设置真正的图片，让图片显示出来----懒加载

   编程方式：
	面向过程   面向对象   函数式编程   链式编程
面向对象:
	就是一个抽象的概念（整体）
		书：
			字数  厚度  作者。。。
	面向对象-》就是数据集与功能集的集合
为什么需要原型：
	构造器创建对象的时候实际上会有成员重复
	解决方法让这个函数共享
	
	工厂模式与构造函数的区别：
		1.工厂模式需要指定对象  返回对象
		2.当前对象 没有办法找到原来的函数（创建出来的函数）
		3.不需要返回值默认返回this
	
	判断当前对象是否属于构造函数：
		console.log(p.constructor)
		console.log(p instanceof Hero)
	实例：由构造函数通过new关键字产生的对象
		实例成员：就是直接可以访问的元素或者属性（就是该对象的元素）；
		静态成员：就是实例不能直接访问(间接)的属性或者对象（就是构造函数的元素）；	
	#######了解为什么要有静态成员：
		框架   jq  需要用到静态成员；
		
	为什么需要使用原型：prototype
		当定义多个函数 那么每执行一次就会调用一次函数 造成内存  function fn(){....方法}。
		解决问题：
			1.把函数定义到全局变量   本质是给当前方法的引用
			2.定义对象  对象里面存放方法  本质是给当前方法的对象下面引用
		js提供了prototype原型对象（本质资源共享）
		
	定义构造函数  经历哪些步骤：
		产生空对象----->产生prototype属性---->建立关系--->返回空对象
	通过new关键字产生对象   经历哪些步骤：
		赋值对象--->产生内存地址：
	实例对象与构造函数与原型对象的关系：
		相对于构造函数：prototype是构造函数的属性。
		相对于实例对象：prototype是实例对象的方法。
	属性搜索原则：
		1.先去构造函数本身上去找
		2.如果构造函数没有该属性  去构造函数的原型去找
		3.如果原型没有找到  要去原型的原型对象去找
		4.如果都没找到属性  最终的执行是null
	属性设置：
		如果实例对象 设置属性 就在本身上设置元素。
	

	1.面向对象的基本概念
    js是不是一个面向对象语言？
        不是： 与传统的面向对象存在冲突；
        是： js面到处都是对象 数组 也可以像传统面向对象的语言那样
2.js的编程风格：
    面向对象的方式编程
    面向过程的方式编程
    函数式。。。。（链式）        
3.面向对象的概念： 面向对象是一个抽象的概念 可以简单的理解为功能集与数据集的集合
    面向过程： 使用过程的方式开发
    面向对象： 使用对象方式开发
4.实例成员与静态成员：
    实例成员：由构造函数创建出来的对象能直接访问的属性和方法  包括：对象本身以及原型
    中的所有的属性和方法
    静态成员：由构造函数直接访问的属性和方法
5.为什么需要原型：
    构造器创建对象的时候  实际上会有成员重复
     解决方式就是让这个方法共享
     每个函数自动有一prototype 属性  称为原型属性
6.属性访问原则：
    1.对象在调用方法的时候 首先在当前对象中查询如果有该成员使用并停止查找
    2.如果没有该成员  就去原型的对象中查找
    3.原型的原型
    4.object.portotype
7.如果修改原型对象中的属性值  实际上给对象添加新成员  并不会修改原来中的对象
8.this 过程：
    1.创建新对象
    2.将构造函数的作用域赋值给新对象
    3.指向原型对象
    4.执行构造函数的方法
		webpack  打包工具！！！
9.自调用函数的方式：
	1.(function(){

	})()
	2.!function(){

	}()
	3.(function(){

	}())
10.继承自己没有， 拿别人的来用 就是自己的一样--继承

	改变this指向  --->在某种环境下执行---->在特定的环境下调用！！！！
	call:改变this指向   
	bind：改变this指向  
	apply：改变this指向  
			三者的区别：改变函数中的this
					1.call(this,name,age)  参数 this指向  具体的参数  会自调用
					2.apply(this,[name,age]) 参数this的指向  具体的参数  要加数组的形式(不代表传的参数是数组) 会自调用   
					3.bind(this,name,age)  参数 this指向  自己不会调用  只是改变this指向
		如果函数内部不传参数 或者传null  就是函数调用  window
继承的方式：
原型继承：
	// function Person(name, age) {
    //     this.name = name;
    //     this.age = age;
    // }
    // Person.prototype.sayhi = function () {
    //     console.log("hello");
    // }
    // function Student() {

    // };

    // Student.prototype = new Person("kf", 20);
    // var stu = new Student();
    // console.log(stu.name)
借用构造函数：
	// 借用构造函数继承：
    // call() 调用构造函数 改变this执行
    // function Person(name, age) {
    //     this.name = name;
    //     this.age = age;
    // }
    // Person.prototype.sayhi = function () {
    //     console.log("hello")
    // }
    // function Student(name, age, sex) {
    //     this.sex = sex;
    //     Person.call(this, name, age)
    // }
    // var stu = new Student("kf", 1, "男");
    // console.log(stu.sayhi());
组合继承：
 // function Person(name, age) {
    //     this.name = name;
    //     this.age = age
    // }
    // Person.prototype.sayhi = function () {
    //     console.log("hello")
    // }

    // function Teacher(name, age, sex) {
    //     Person.call(this, name, age)
    //     this.sex = sex
    // }
    // Teacher.prototype = new Person();
    // var tea = new Teacher(name, age, sex);
快速继承：
	 var o = { name: "kf", age: 20 };
    var obj = Object.create(o);
    console.log(obj)
	内部的封装
	// function create(o) {
    //     function F() { };
    //     F.prototype = o;
    //     return new F();
    // }
    // var obj = create(o);
    // console.log(obj)


函数：
	函数的调用：
		函数式调用： 函数名调用（）
		方法调用： obj.方法
		构造函数调用： new 
		上下文调用：  call   apply   bind；
	this:
	window：
		1.函数式调用 window
		2.回调函数 函数以参数形式传递 
		3.定时器  延时器  window
	方法调用：
		指向直接调用的方法对象
	构造函数调用：
		不加return 默认返回this
		return  {} []  this指向就是当前返回的对象
		return 1; this指向还是当前实例对象

闭包：
	
	函数的执行过程：
		调用函数	（创建内存地址）
			1.进栈  （进入执行环境）
			2.压栈   执行当前环境的代码
			3.出栈  返回执行环境
			4.销毁  内存空间
	闭包： 1.一个封闭的执行环境（隔离区域）  2.一个作用域可以访问另一个作用域的变量   沙箱模式！！！   一个具有作用域隔离特性的一个内存结构，
	即为一个闭包
	闭包到底要解决什么问题：
		在js当中要解决的问题 就是间接的访问到这个被隔离的数据。
	使用return 数据不能直接访问原来的数据  可以利用函数的返回访问原始数据

	缺点：占用内存！！！
		一个函数内部返回一个函数  函数里面引用着外部函数的变量；
	特点：延展作用域;

	递归：  自己调用自己 一定要有结束条件

		切记：  递归注重的是思想 结果  而不是过程；


// 浅拷贝： 拷贝的是属性 对于对象 拷贝的引用
	// function copy(o1, o2) {
	// 	for (var k in o1) {
	// 		o2[k] = o1[k]
	// 	}
	// }
	// copy(obj, obj1)
// 深拷贝: 拷贝的是属性 对于对象 拷贝的是具体的值
	// function deepcopy(o1, o2) {
	// 	for (var k in o1) {
	// 		if (o1[k] instanceof Array) {
	// 			o2[k] = [];
	// 			deepcopy(o1[k], o2[k])

	// 		} else if (o1[k] instanceof Object) {
	// 			o2[k] = {};
	// 			deepcopy(o1[k], o2[k])
	// 		} else {
	// 			o2[k] = o1[k]
	// 		}
	// 	}
	// }
	// deepcopy(obj, obj1)
	函数的其他成员：
		name：函数的名字;
		arguments:实参的伪数组;
		arguments.callee打印当前的函数   arguments.callee();

	正则表达式：  
		创建正则表达式：
			var reg = //;
			var reg = new RegExp("正则表达式","匹配模式")
		reg.test(匹配对象)
		是一个正则匹配的对象  该对象可以对字符串进行 提取  替换  匹配；	
	元字符：  
		\d:匹配数字的（所有的数字）
		\D:匹配非数字
		\n:换行符
		\w:数字 字母 下划线
		\W:非数字字母 下划线

		* : 紧接着前面的一个字符0次或多次  
		+：紧接着前面的一个字符 出现1次或多次
		?:0次或1次
		a{3}  aaa  指定次数
		a{3,}  最少3次
		a{1,3}紧跟前面的字符出现的范围
		1(23)* 表示紧跟着前面的一组
		a-z  0-9  A-Z  [0-9a-zA-Z] 
	基本元字符：
				. 表示任一个非换行的字符
				() 分组 提高优先级
				[] 表示一个字符	 [ab] 
				| 或者
				转移字符： \  \.
	提取：
		exec()  每次只能提取一个;  	
		match() 提取多个 注意是字符串的方法
贪婪模式：  尽可能提取（查找）很多的数据；
非贪婪模式：尽可能提取（查找）少量的数据；
?改变贪婪模式；




  





















        

		

			 