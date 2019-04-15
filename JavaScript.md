
###变量:暂时存储一个数据的容器
### 数组:暂时存储一组数据的容器

###5 种不同的数据类型：

### string 字符串
### number 数字
### boolean 布尔值 true flase
###object 对象
###function 函数


###3 种对象类型：	

### Object对象
### Date 时间
### Array 数组


###2 个不包含任何值的数据类型：

### null 空
### undefined 未定义

### 声明一个变量 

var i= 0;
if(i==0){
 consol.log("等于");
}else{
  consol.log("不等于");
}

break;
###跳出
continue 
###跳出并继续
###函数 哪里调用就放哪里 test();
 function test(demo){

if(demo == 0){
 consol.log("等于");
}else{
  consol.log("不等于");
}

}
test(5);

###for 
###for in for(x in array）

###for in 自动循环 不用带下标

 var array = new Array();
    var x;
    var txt=""
    array[0] = 1;
    array[3] = 2;
    array[4] = 3;
    array[10] = 4;
    for( x in array ){
        alert(array[x]);     // 依次显示出 1 2 3 4
    } 
    alert(array.length);    // 结果是11
    for( var i=0 ; i<4 ; i++){
        alert(array[i]);     // 依次显示出 1 undefined undefined 2 
    }
    document.getElementById("demo").innerHTML = txt;


### while

while (i<5)
{
    x=x + "The number is " + i + "<br>";
    i++;
}

//do while 

do
{
    x=x + "The number is " + i + "<br>";
    i++;
}
while (i<5);
###typeof 检测变量的数据类型
var str = 1;
typeof(str)

###正则表达式 search() replace() test()
###search()
var str = "Hello GC!"; 
var n = str.search(/GC/i);

###i是修饰符, 搜索不区分大小写 空格算下标

###replace()

var str = document.getElementById("demo").innerHTML; 
var txt = str.replace("Microsoft","Runoob");
###把Microsoft 替换成 hello world

### test();
var patt = /e/;
patt.test("The best things in life are free!");
###输出 e

### match()
### 如果没有找到任何匹配的文本， match() 将返回 null。否则，它将返回一个数组，


### 正则修饰符
i ###不区分大小写
g ###执行全局匹配 （查找所有匹配而非在找到第一个匹配后停止）
m ###执行多行匹配。

###正则表达式模式
[abc]	
###查找方括号之间的任何字符。
[0-9]

###查找任何从 0 至 9 的数字。
(x|y)
###查找任何以 | 分隔的选项。

### 元字符是拥有特殊含义的字符

d	
###查找数字。
s
###查找空白字符。
b	
###匹配单词边界。
uxxxx	
###查找以十六进制数 xxxx 规定的 Unicode 字符。

###量词

### n+	匹配任何包含至少一个 n 的字符串。
### n*	匹配任何包含零个或多个 n 的字符串。
### n?	匹配任何包含零个或一个 n 的字符串。

### try catch 关于捕获异常 try尝试 catch 捕获异常  finally 捕获结束后 throw 创建或抛出异常（exception）


function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try { 
    if(x == "") throw "值是空的";
    if(isNaN(x)) throw "值不是一个数字";
    x = Number(x);
    if(x > 10) throw "太大";
    if(x < 5) throw "太小";
  }
  catch(err) {
    message.innerHTML = "错误: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}

### 严格模式  "use strict" 的目的是指定代码在严格条件下执行。严格模式下你不能使用未声明的变量。
### Return 语句使用注意事项
### JavaScript 默认是在代码的最后一行自动结束。

### this 关键字
<!-- 
在方法中，this 表示该方法所属的对象。
如果单独使用，this 表示全局对象。
在函数中，this 表示全局对象 也就是window。
在函数中，在严格模式下，this 是未定义的(undefined)。
在事件中，this 表示接收事件的元素。
类似 call() 和 apply() 方法可以将 this 引用到任何对象。 
-->

<!-- var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
}; -->
 
### this上下文
### call
<!-- var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
var x = person1.fullName.call(person2); // 返回 "john Doe  
当我们使用 person2 作为参数来调用 person1.fullName 方法时, this 将指向 person2, 即便它是 person1 的方法：
--> 

### call 和apply方法 相同点：“可以用来代替另一个对象调用一个方法，将一个函数的对象上下文从初始的上下文改变为由thisObj指定的新对象
###                    不同点：apply：最多只能有两个参数


### let const
### let 它只在 let 命令所在的代码块 {} 内有效。
### const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改

### JSON 英文全称 JavaScript Object Notation
### JSON 是一种轻量级的数据交换格式。
### JSON是独立的语言 *
### JSON 易于理解。
{"sites":[
    {"name":"Runoob", "url":"www.runoob.com"}, 
    {"name":"Google", "url":"www.google.com"},
    {"name":"Taobao", "url":"www.taobao.com"}
]}


### 闭包

function add() {
    var counter = 0;
    return counter += 1;
}
 
add();
add();
add();
 
// 本意是想输出 3, 但事与愿违，输出的都是 1 !

var add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();
 
add();
add();
add();
 
// 计数器为 3

<!-- 变量 add 指定了函数自我调用的返回字值。

自我调用函数只执行一次。设置计数器为 0。并返回函数表达式。

add变量可以作为一个函数使用。非常棒的部分是它可以访问函数上一层作用域的计数器。

这个叫作 JavaScript 闭包。它使得函数拥有私有变量变成可能。

计数器受匿名函数的作用域保护，只能通过 add 方法修改。 -->

### DOM 文档对象模型  

   # onload 加载完成 
   # onunlod 离开执行
   # onchange当用户改变输入字段的内容时
   # onmouseover 移入
   # onmouseout  移出
   # onmousedown 鼠标按下
   # onmouseup 鼠标释放
   # onclick 点击
   # onfocus 获取焦点
   # onblur 失去焦点

   ### dom2级监听
   #addEventListener() 
   #阻止事件冒泡 stopPropagation()
   #阻止默认事件 preventDefault();

###节点的创建


var para = document.createElement("p");
var node = document.createTextNode("这是一个新的段落。");
para.appendChild(node);
var element = document.getElementById("div1");
element.appendChild(para); //appendChild是尾部添加
insertBefore() 开始位置添加
removeChild()移除节点
replaceChild()替换节点
#完成并添加进去