## 第一节课：JavaScript简介

### 一、能做什么：

1. 数据的验证
2. 将动态的文本写入到网页当中
3. 可以对事件作出响应
4. 可以读写html中的内容
5. 可以检测浏览器
6. 可以创建cookies

### 二、特点

基于对象和事件驱动的松散的解释性语言

1. javascript面向对象开发的
2. 事件驱动
3. 松散型 弱类型
4. 解释性的语言

### 三、历史

JScript

scriptease

javascript

ECMAscript

### 四、javascript的构成

1. ECMAscript（语法）
2. BOM browser object model
3. DOM document object model

### 五、如何入门

1. html css xml
2. 开发工具

----------------------------------------------------------------------------------------------------------------------------------------------------------------

## 第二节课：javascript的放置和注释

### 一、输出工具

1. alert("");//全局函数

2. document.write("");//

3. prompt("提示性语句","(可以选择设置默认的值，也可以由用户自己输入)");//返回用户输入的值

### 二、javascript如何在html中进行放置

1. \<script type="text/javascript" language="javascrit">\</script>：标签对的形式。javascript可以在html页面的任何位置进行调用，但他们还是一个整体，是相互联系的。相互影响的。
2. 可以在超链接或是重定向的位置调用javascript代码

```html
<a href="javascript:alert('');">链接</a>


<form action="javascript:alert('');" method="post"></form>
```

3. 在事件后面调用

```html
1.第一种
<div onclick="[javascript:]alert('')">
    //javascript是可有可无的
</div>    



2.第二种
<script for="idname" event="onclik">alert("");</script>
			 |
			 |
		     \/
<div id="idname">...</div>

```

4. 调用外部javascript文件

```html
<script src=""></script>//中间不能加代码
//src指向js文件地址，外部的javascript文件不需要使用script标签
//只要使用的是标准的script语法，文件后缀可以是txt或其他
```

### 三、注释

1. 对付旧版的浏览器

```html
<!---->
```

2. 真正的注释符号

```html
//行内注释

/*多行注释*/
```



## 第三节课：javascript变量和数据类型

### 一、javascript命名规范

1. 严格区分大小写
2. 变量命名必须以字母、\_或$开头，余下的部分可以是任意的字母、数字或者是\_、$
3. 不能用关键字或保留字命名
4. javascript自己的命名规范：驼峰命名法、首字母大写
5. 命名一定要有意义
6. ;的用法

### 二、javascript变量

1. 变量：可以存储数据的一个容器

2. 创建（声明）变量：以var关键字修饰

   a. 先声明后赋值（var a; a="...";）

   b. 声明和赋值同时进行（var a="...";）

   c. 一次声明多个变量，再赋值（var a,b,c...; a="..."; b="..."; c="...";...）

   d. 一次声明多个变量同时赋值（var a="..",b="...",c="..."...;）

3. 如何覆盖已有的变量

   a. 如果重复声明该变量，而没有赋值，该变量的值不会改变

   b. 如果重新声明该变量并且重新赋值，那么旧的变量值会被新的值所覆盖

4. 如果不用var修饰变量，且没有赋值，那么javascript会不执行该代码；如果赋值了，那么javascript会将它作为全局变量，并且自动为它设置类型，但是不推荐使用

### 三、javascript中的数据类型

1. 初始类型

   Undefined：指的就是变量创建后没有赋值，而变量的默认值就是undefined

   Null：指的是什么都没有，仅仅是一个占位符。typeof(null)==Object

   Number：包括整型和浮点型，支持二进制、八进制（以0开头，后面的数不能超过8，超过就会直接认为是十进制数）、十进制、十六进制（以0x开头），用科学计数法（e来表示某个数的10次方，2e+1=20,2e-1=0.2）来表示，还包括一些特殊的值

   ​			Number,MAX.VALUE(最大值)

   ​			Number.MIN.VALUE(最小值)

   ​			Number.POSITIVE_INFINITY

   ​			Number.NEGATIVE_INFINITY

   ​			Infinity(无穷大)

   ​			-Infinity(无穷小)

   

   ​			isFinite()判断一个数是否是无穷的

   ​			NaN         not a number,系统提示

   ​			isNaN()    not a number? 不能转换为数字返回为真，能转换为数字返回假

   String：用单双引号来说明，所包围的值都是字符串，还包括一些特殊字符（转义字符）。

   ​			单双引号的用法：效率一样，只能成对出现，不能交叉使用，又可以嵌套使用

   Boolean：只有两个值，true(1)，false(0)

2. 引用类型

   Object(class)：包含相关属性和方法的一个集合

   ​				new 关键字

   ​				var a = new Object();

   ​				a={};

3. typeof操作符

   用来检测数据类型的一元运算符，并且返回的结果始终是一个字符串

## 第四节课：运算符

### 一、运算符和操作数的组合就是表达式

### 二、JS运算符

1. 算术运算符

   +，-，*，/，%,++var,var++，--var，var--

   加号：用于数值的运算；用于字符串的连接；任何的数据类型和字符串相加都是字符串类型

   取余：用于取一范围的值；一般不用于小数，因为结果不确定

   ++，--

2. 关系运算符（比较运算符）

   <，>，<=，>=，==，===，!=，!==

   a. 运算的结果都是布尔值

   b. 都是字符串的时候，会先转换为ascll码再比较它们的第一个字母

   c. 都是数值的时候正常比较

   d. 当字符串与数值进行比较时，会尝试将字符串转换为数值类型，再进行比较，如果不能进行转换，则会一次返回NaN，和false

   e. undefined==null

   f. 如果两个都是数值类型的字符串做比较，则只比较第一个数

   g. 如果一个数值和boolean进行比较，会把布尔值转换为数值再进行比较，true为1，false为0

   -------------------------------------

   ==	!=	只比较值是否相等

   a. 比较字符串时是比较它们的ASCLL码是否相等

   b. 比较两个数值的时候，比较他们的数值是否相等

   c. 比较函数时，判断他们的位置是否相等

   ------

   ===	!==	不但比较值是否相等，还比较类型是否相等

3. 赋值运算符（=）

   =	+=	-=	*=	/=	%=

   -----

   +=

   用于数值的运算；用于字符串的连接；任何的数据类型和字符串相加都是字符串类型

4. 逻辑运算符（布尔运算符）

   a. 与 and &&	或or ||	非not !

   b. &&——一假即假

   c. ||——一真即真

   d. ！——非真即假

   e. 逻辑运算符可以对任何类型的数据进行运算，但是在运算的时候，可以转换为对应的布尔值

   f. undefined与null为false；除0以外都是真的；对象也是真的；除了空字符串都是真的

   g. 类变量进行赋值

   ​		var a = b && c

   ​		如果一个运算数是对象，另一个是boolean值，返回该对象

   ​		如果两个运算符都是对象，返回第二个对象

   ​		如果某个运算符是null，返回null

   ​		如果某个运算符是NaN，返回NaN

   ​		如果某个运算数是undefined，发生错误

   ​		var a = b || c

   ​		如果一个运算数是对象，并且该对象左边的运算数值均是false，则返回该对象

   ​		如果两个运算数都是对象，则返回第一个对象

   ​		如果最后一个运算数是null，并且其他运算数值均为false，则返回null

   ​		如果最后一个运算数是NaN，并且其他运算数值均为false，则返回NaN

   ​		如果某个运算数是undefined，发生错误

5. 一元运算符

   typeof	+	-	delete	new	++	--

   a. 这里的+是正号，表示正数

   b. delete：删除对象的方法或属性

   c. new：用来创建一个对象

6. 特殊的运算符

   ,	()	= ? :

   a. ，：用来一次声明多个变量

   b. () ：运算过的时候有优先级的作用；运行一段函数

   c. 三元运算符：根据表达式的计算结果有条件的为变量赋值

   ​	格式：var 变量=布尔表达式？真值：假值；

7. 位运算符

## 第五节课：JS数据类型强制转换

### 一、转换为数值类型（Number）

Number(参数)：把任何的类型转换为数值类型

1. 如果是布尔值，则true转换为1，fase转换为0

2. 如果是数字则转换为本身，将无意义的后导0去掉

3. 如果是null，转换为0

4. 如果是undefined则转换为NaN

5. 如果是对象则会先调用对象的valueof()，如果valueof()返回的是NaN，然后再调用对象的toString()

6. 如果是字符串

   ​		a. 如果字符串当中只有数字，转换为十进制（忽略前导0和后导0）

   ​		b. 如果是有效的规范的浮点型，转换为浮点值（忽略前导0和后导0）

   ​		c. 如果是空字符串，转换为0

   ​		d. 如果是其他值，返回NaN

parseInt(参数1，参数2)：将字符串转换为整数

1. 如果一个字符串只包含数字，则以十进制的方式转换为整型
2. 它会自动忽略字符串前面的空格，直到找到第一个非空的数值字符串，直到解析到第一个非数值的字符串就结束
3. 如果字符串的第一个字符是空格、数字、-（负号），那么就会返回NaN
4. 参数1支持数值类型：八进制（0开头），十进制，十六进制（0x开头）
5. 参数2控制输出模式：2~32的任意进制输出

parseFloat()：将字符串转换为浮点数

1. 字符串当中的点只有第一个有效，其它的都无效
2. 如果字符串是一个有效的整数，返回的就是整数，不会返回浮点数

### 二、转换为字符串类型（String）

String(参数)：可以将任何类型转换为字符串

1. null和undefined都会转换为字符串，分别是null和undefined
2. 布尔类型会返回true和false
3. 数值类型会返回本身的字符串

toString()

1. 格式：对象.toString()
2. 将对象以字符串的方式来表示
3. 数组.toString()：由逗号分割的字符串
4. 布尔.toString()：两个值，true和false
5. String.toString()：返回本身
6. Number.toString(参数)：返回本身的字符串形式，参数控制输出格式
7. null和undefined没有toString()

### 三、转换为布尔类型（Boolean）

Boolean()：可以将任意类型转换为布尔值

1. 转换为假：""(空字符串)、0、NaN、undefined、false
2. 其他的全部转换为真

## 第六节课：JS数据类型隐式转换

### 一、函数类

​	1. isNaN()：该函数会对参数进行隐式Number()转换，如果转换不成功则返回true

​	2. alert()：输出的内容会隐式的转换为字符串

### 二、运算符类

	1. 算术运算符：-	*	/	%；如果操作数不是数值，将会隐式的调用Number()函数，按照这个函数的转换规则进行转换，如果转换不成功，整个表达式返回NaN
 	2. +：如果操作数都是数值，然后进行相加；任何数据类型和字符串相加都会隐式的调用toString()，然后返回它们拼接的结果；如果操作数都是boolean值那么进行Number()抓暖，false为0，true为1，然后进行相加
 	3. 关系运算符：关系运算符的操作数可以是任何类型，如果操作数不是数值类型，将会隐式的转换
 	4. 等性运算符：==	!=；会对操作数进行隐式的转换再比较值；如果其中至少有一个是布尔值，会隐式的调用Number()，然后进行比较；如果一个为字符串，另一个为数值，也会隐式的调用Number()对字符串进行转换，如果转换不成功，则返回false；undefined==null
 	5. 逻辑运算符：放在表达式里面用于判断；给变量赋值

### 三、语句类

```javascript
if(表达式){}else{}
var 变量=Boolean expression?真值:假值;
while(){}
/*if语句和三元表达式、循环语句里面的表达式会隐式的调用Boolean()函数，按照这个函数的转换规则，转换为响应的布尔值*/



```



## 第七节课：流程控制---分支结构

​			就是程序代码的执行顺序

​			通过规定的语句，让程序代码有条件的按照一定的方式执行

### 一、顺序结构

按照书写的顺序来执行，是程序中最基本的流程结构。

### 二、选择结构（分支结构、条件结构）

根据给定的条件有选择地执行相应的语句。

if	else if	else

1. 单路分支：条件可以是任何类型的数据或表达式；大括号会把里面的代码作为一个整体执行，如果只有一条语句可以省略大括号

   if(条件){条件成立执行的语句}

2. 双路分支：

   if(条件){条件成立时执行代码}else{条件不成立时执行代码}

3. 多路分支：

   if(条件1){条件1成立时执行的代码}else if(条件2){条件2成立时执行的代码}...else{所有条件都不成立时执行的代码}

4. 嵌套分支：在条件分支里在分支

switch

1. 语法：

   switch(任意类型的变量){case 值1:表达式；break;case 值2:表达式；break;case 值3:表达式；break;...default : 表达式}

2. 当判断范围的时候用if

3. 当判断单个值的时候用switch

4. 条件满足的情况不可以重复，会发生不可预期的错误

### 三、循环结构

在给定的条件满足的情况下反复地执行同一段代码

1. for

   for(变量=初始值;变量<=结束值;变化值){循环体}

2. while

   当条件满足时执行循环体，当不满足时退出循环

   while(){}

3. do...while

   最少执行一次，在进行条件的判断，如果条件满足继续执行，如果不满足则退出循环

   do{}while()

4. for in

5. while：先判断后执行；do...while：先执行一次再判断

6. for一般用于循环指定的次数；while是根据条件的真假来循环，当真的时候循环，假的时候退出循环

## 第八课：流程控制---跳转语句、with语句

### 一、跳转语句

在循环控制语句中，当满足指定条件的时候，退出循环或者是推出当前循环的语句

1. break：格式：break;	跳出并终止循环，如果后面有代码，则继续往下执行

   用在switch当中，指当满足某个条件后，退出switch语句

   用在循环语句当中，跳出并终止循环，如果后面又代码，则继续往下执行

2. continue：格式：continue;	跳出并且终止当前的循环，如果下个值仍满足循环跳进，则继续循环

   只能用在循环语句当中

   最好用适当的语句代替continue

### 二、标签语句

用来退出多层循环

格式：标签名：语句;

标签名可以作用于break或continue

### 三、with语句（效率较低）

语法：with(){}

用于设置代码在特定对象中的作用域

不建议使用

## 第九课：函数的声明和调用

将完成某一特定功能的代码集合起来，可以重复使用的代码块

### 一、函数的声明方式

1. 基本语法：function	关键字

   function	函数名(\[参数1],\[参数2]...){

   ​		函数体

   ​		[return ;]//返回值可选

   }

2. 字面量定义的形式（匿名函数）

   语法：var	变量 =function(\[参数1],\[参数2]...){

   ​		函数体

   ​		[return ;]//返回值可选

   }

3. 以对象的形式来声明

   new	关键字

   语法：var	变量=new	Function(\[参数1],\[参数2]...,函数体);

### 二、函数的调用方式

1. 函数名()，变量名()
2. (function 	函数名(){})();

### 三、两种声明方式的区别

1. 如果两个函数的命名相同，后面的会覆盖前面的函数
2. 以基本语法声明的函数，会在代码运行的时候，提前加载到内存当中，以供以后使用，但是以字面量形式命名的函数，会在执行的时候，才进行赋值
3. 在不同的script块中函数，使用和调用的时候，应该先定义，后执行

## 第十课：函数的参数、return语句

### 一、参数（最多25个）

可以动态的改变函数体内对应的变量的类型或值，使同意函数体得到不同的结果

形参：在定义函数的时候，函数括号中定义的变量叫做形参

实参：在调用函数的时候，在括号中传入的变量或值叫做实参

1. 参数的类型

   可以是任何的数据类型

2. 参数的个数（最多25个）

   1. 实参和形参的数量相等，一一对应

   2. 形参的数量多余实参

      不会报错，但是多出的参数的值会自动赋值为undefined

   3. 实参的数量多余形参

      1. 不会报错，但是要得到躲到的实参的值，要用arguments对象

### 二、arguments对象

每创建一个函数，该函数都会隐式的创建一个arguments对象，它包含有实际传入参数的信息

1. length	检测实际传入参数的个数
2. callee	对本身的调用

访问每个传入参数的具体的值（arguments[下标]）

### 三、函数重载

同一个函数因为参数的类型或数量的不同，可以对应多个函数的实现，每种实现对应的函数体

### 四、return语句

1. 停止并且跳出当前的函数
   1. 在return语句后面的函数体内所有内容都不会输出
   2. 在函数体内可以有多个return语句，但只会执行一个（判断语句）
2. 给函数返回一个值
   1. 语法：return	返回值；
   2. 返回值可以是任何数据类型
   3. 只能返回一个返回值
   4. 如果函数没有返回值，那么这个函数的值就会自动赋值为undefined

## 第十一课：解析顺序和变量作用域

作用域：指的就是一段代码的作用范围

### 一、变量的作用域

1. 全局变量
   1. 在代码中任何位置都能访问得到的变量，拥有全局的作用域
      1. 最外层函数外面定义的变量
      2. 没有定义直接赋值的变量，拥有全局属性（即不使用var定义的变量都是全局变量）
      3. 网页所有的脚本和函数都可以访问
      4. 没必要不创建全局变量
      5. 自定义的全局变量（函数）能够覆盖window变量（函数）
      6. 任何函数，包括window对象，可以覆盖自定义的全局变量或函数
   2. 严格模式
      1. 不会自动创建全局变量
   
2. 局部变量
   1. 只能在固定的代码片段（函数片段）中访问得到
      1. 函数内部定义的变量，就是局部变量
      2. 函数参数也是局部变量
   2. 可以提高程序的逻辑性和安全性，减少名字的冲突
   
3. 块作用域

   1. 使用let关键字定义

   ```js
   {
       let a = 10;
   }
   ```

   2. 块作用域内的变量不能被外部使用
   3. 在外部使用var定义的变量到块作用域中使用var定义会改变域外的变量的值
   4. 而在块作用域内使用let重新定义外部变量则不会改变外部变量的值

4. 全局作用域

   1. window
   2. 所有全局变量均属于window对象

5. 变量的有效期

   1. 变量的有效期始于被创建时
   2. 局部变量会在函数完成时被删除
   3. 全局变量会在关闭页面时被删除

### 二、JS预解析顺序

1. \<script>\</script>块依次解析
2. 解析代码运行的环境
3. 对标识符（关键字var	function）进行解析，解析到相应的环境下
4. 如果还有\<script>\</script>块再按照上面的步骤依次解析

### 三、名词解释

环境：

1. 宿主环境

2. 执行环境

   执行的环境决定了变量和函数的访问权限

   1. 全局环境
   2. 函数环境
   3. eval()；

作用域：

​		一段代码的作用范围

作用域链：

​		在一个执行环境中有权访问的变量和函数能够有序有机的访问

## 第十二课：回调函数、递归函数

### 一、回调函数

通过函数的指针来调用函数

（把一个函数的指针作为另一个函数的参数，当调用这个参数的时候，这个函数就叫做回调函数）

1. 通过函数指针来调用

```js
function math(num1,num2,fun){
	return fun(num1,num2);
}

function aa(num1,num2){
    return (num1+num2)*2-1;
}
function bb(num1,num2){
    return (num1-num2)*3-2;
}


//下面进行调用，使用aa函数来进行计算
//这就是使用函数的指针来进行回调
math(2,3,aa);
```

2. 通过匿名函数来调用

```js
function math(num1,num2,fun){
    return fun(num1,num2);
}

//下面通过匿名函数来进行调用
math(1,2,function(num1,num2){
    return (num1+num2)*2-3;
})
```

3. 定义和调用同时进行

```js
alert((function math(num1,num2,fun){
    return fun(num1,num2);
})(1,2,function (num1,num2){
    return (num1+num2)*3-1;
}));
```

### 二、递归函数

在函数内部直接或间接的调用自己

### 三、内嵌函数（闭包）



## 第十三课：内置顶层函数

### 名词解释：

1. 函数
2. 内置：ECMAscript	DOM	BOM
   1. 内置函数：ECMAscript自带的函数	Number()
   2. 宿主函数：BOM	DOM	alert()	prompt()	confirm()
3. 顶层
   1. 字符串函数：字符串.函数()
   2. 数组函数
   3. 顶层对象的函数，可以作用于任何对象

### 内置顶层函数

1. escape()	对字符串进行编码
2. unescape()	对编码的字符串进行解码
3. Number()----转换成数值类型
4. String()----转换成字符串类型
5. Boolean()----转换成布尔类型
6. parseInt()----将字符串转换成整型
7. parseFloat()----将字符串转换成浮点型
8. isNaN()----判断一个数能否转换成数值类型
9. isFinite()----判断一个数是否为有穷的数字，将不是有穷的数字和不能转换为数值类型的数返回false
10. eval()----将字符串转换成javascript命令执行（必须符合JavaScript语法规范，否则会出错）
    1. window.eval()----全局生效
    2. execScript()----IE中使用

## 第十四课：数组

数组是一个可以存储一组或是一系列相关数据的容器

只支持一维数组

长度可变

如果是索引数组，下标从0开始，如果指定了长度但没有赋值，会自动赋值为undefined

### 一、为什么要使用数组

1. 为了解决大量数据的存储和使用的问题
2. 模拟真实的世界

### 二、如何创建数组

JS数组可以存储任何类型的数据

1. 通过对象的方式来创建

   1. 语法：var	a = new	Array()
   2. 直接赋值：var	a = new	Array(元素1，元素2...)
      1. var	a = new	Array(数值)
      2. 如果只有一个元素，并且这个元素是数值类型，那么他就是指定数组的长度，并且值都是undefined
      3. 数组的属性：length属性
   3. 声明以后再赋值
      1. 语法：var	a = new	Array()
      2. a[0]=1
      3. a[1]=2
      4. a[2]=3

2. 隐形声明的方式

   语法：var a = [ ];

   1. 直接赋值：var a = [1，2，3...];
   2. 声明以后再赋值

### 三、访问数组的元素

通过数组的下标访问，数组下标从0开始，最大长度为length-1

### 四、遍历数组的元素

1. for循环
2. while语句
3. for	in：类似foreach遍历
   1. 用于数组的遍历
   2. 用于对象属性的遍历

### 五、数组的分类

1. 下标的类型

   1. 下标是数字类型的是索引数组
   2. 下标是字符串类型的是关联数组

   ```JS
   var a = [];
   a["name"]="zhangsan";//关联数组
   a[1]=2;//索引数组
   
   alert(a["name"]);
   alert(a[1]);
   ```

2. 维度来分类

   1. 一维数组
   2. 二维数组
      1. 声明：var a = new Array(\[ ],\[ ],\[ ]...);或者var a = \[\[],\[]...];
   3. 多维数组

## 第十五课：JS对象基础

### 一、名词解释

1. 基于对象：一切皆对象，以对象的概念来编程
2. 面向对象编程：OOP
   1. 对象：就是人们要研究的任何事物，不仅能表示具体事物，还能表示抽象的规则，计划或事件。属性的无序集合，每个属性可以存一个值（原始值，对象，函数）
   2. 对象的属性和行为
      1. 属性：用数据值来描述它的状态
      2. 行为：用来改变对象行为的方法
   3. 类：具有相同或相似的性质的对象的抽象就是类。对象的抽象就是类，类的具体化（实例化）就是对象

### 二、创建对象

1. 构造函数方法

```js
//构造函数
function fun(){}
var obj = new fun();
```

2. object方法

```js
//object方法
function object(){}
//或者
var a = new Object();
```

3. json方法（javascript object notation）：原生格式

```js
//json方式
var a = {}
```

   

### 三、如何添加属性和方法

如果属性的值是函数，就叫对象的方法，否咋就叫属性

1. 构造方法
   1. 声明的时候添加
   2. 声明以后再添加
2. json方法
   1. 声明的时候添加
      1. 格式：var obj = {属性名:属性值，属性名:属性值,...};
   2. 声明以后再添加

### 四、访问对象的属性和方法

引用值.属性

引用值.属性()

```js
//声明之后赋值

function fun(){}
var obj = new fun();//实例化对象
obj.name="zhangsan";//添加一个属性
obj.say=function (){return "说话"}//添加一个方法

alert(obj.name);
alert(obj.say());


//声明时添加
function fun(){
    this.name="zhangsan";
    this.say() = function (){
        return "说话";
    }
}
var obj = new fun();//实例化对象
```

```js
//声明的时候添加
var obj = {name:"zhangsan",say:function (){return "说话"}};

alert(obj.name);
alert(obj.say());


//声明之后再添加
var obj = {};
obj.name = "zhangsan";
obj.say = function (){
    return "说话";
}
alert(obj.name);
alert(obj.say());
```

### 五、如何销毁对象

javascript自己的垃圾回收机制：就是在对象没有引用的时候释放内存（销毁）

对象=null；（手动销毁）

### 六、如何删除对象的属性

delete

```js
var obj = {name:"zhangsan",say:function (){
return "说话";
}}

delete obj.name;
delete obj.say();
```

## 第十六课：对象的遍历、内存分布和封装特性

### 一、JS对象的遍历

1. js属性访问

   对象.属性

   对象[属性]//字符串格式

2. js属性的遍历

   1. for in：

      ```js
      var ren = {}
      ren.name="zhangsan";
      ren.say = function (){
      	return "说话";
      }
      
      for(var i in ren){
          alert(i);
      }
      ```

### 二、内存分布

### 三、对象的特性之封装

把对象所有的组成部分组合起来，尽可能隐藏对象的部分细节，使其受到保护。只保留有限的接口和外部发生联系

1. 工厂函数（不推荐）

```js
//工厂函数
function dianshi(color,size,brand){
    var tv = {}
    tv.color=color;
    tv.size=size;
    tv.brand=brand;
    tv.look=function (){
        return "看电视";
    }
    tv.play = function (){
        return "打游戏";
    }
    tv.dvd = function (){
        return "DVD";
    }
    return tv;
}


var obj = dianshi("red","30inch","sony");
alert(obj.name);
```

2. 构造方法的形式

```js
//构造方法的形式
function tv(color,size,brand){
    this.color=color;
    this.size=size;
    this.brand=brand;
    this.look=function (){
        return "看电视";
    }
    this.play = function (){
        return "打游戏";
    }
    this.dvd = function (){
        return "DVD";
    }
}
var sony = new tv("red","30inch","sony");
alert(sony.color);
```

3. prototype方法：不能共享对象（会产生信息安全问题）

```js
function tv(color,size,brand){
    this.color=color;
    this.size=size;
    this.brand=brand;
    this.look=function (){
        return "看电视";
    }
}
	tv.prototype.play = function (){
        return "打游戏";
    }
    tv.prototype.dvd = function (){
        return "DVD";
    }
var sony = new tv("red","30inch","sony");
alert(sony.color);
```

4. 混合方式

## 第十八课：JS对象的继承和Object对象

对象的一个类可以从现有的类中派生，并且拥有现有的类的方法或是属性，这个过程叫做继承。被继承的类叫父类或基类，继承的类叫子类。

（一个对象拥有另一个对象的属性和方法）

优点：

​	提高代码的重用性

​	提高代码的可维护性

​	提高代码的逻辑性

### 一、Object对象

​	var obj = new Object();

1. 属性：
   1. constructor
      1. 对创建对象的函数的引用（指针）
   2. prototype	原型
      3. 对该函数对象的对象原型的引用，是函数对象的默认属性
         1. 对象的共享属性存放到代码段当中
         2. 可以实现继承
      4. 方法：
         1. hasOwnProperty(property)
         2. 判断对象是否有某个特定的属性
         3. isPorototypeOf(object)
         4. 判断对象是否为另一个对象的原型，用来检测对象的类型
      5. 运算符：
         1. instanceof

### 二、继承

1. 原型继承

```js
function person(){
    this.name="zhangsan";
    this.say = function (){
        return "说话";
    }
}
function student(){
    
}

student.prototype = new person();
var zhangsan = new student();
alert(zhangsan.name);
```

2. 对象冒充的形式

   1. 格式：ob1.method.call(obj2,[参数1，参数2......])
   2. 让对象1的方法冒充对象2的方法

   ```js
   function person(){
       this.name="zhangsan";
       this.say = function (){
           return "说话";
       }
   }
   function student(){
   }
   
   var ren = new person();
   var zhangsan = new student();
   ren.say.call(zhangsan);
   
   ----------------------------------------
   
   function person(){
       this.name="zhangsan";
       this.say = function (){
           return "说话";
       }
   }
   function student(){
       window.person.call(this);
   }
   
   var zhangsan = new student();
   alert(zhangsan.name);
   ```

   3. apply
   4. 格式：obj1.method.apply(obj2,[参数1，参数2，....])（其中后面的参数必须以数组的形式加入）

## 第十九课：JS对象的继承顺序、分类和内置math对象

### 一、对象的继承

```js
Object.prototype.say=function (){
    return "说话";
}
Objcet.prototype.say=function (){
    return "我是object的原型";
}
function person(){
    this.say=function (){
        return "我是父类";
    }
}
person.prototype.say=function (){
    return "我是父类的原型";
}
function study(){
    this.say=function (){
        return "我是子类";
    }
}
study.prototype.say=function (){
    return "我是子类的原型";
}
study.prototype = new person();
var zhangsan = new study();
alert(zhangsan.say());
```

### 二、对象的分类

1. 内置对象
   1. Global
   2. Math
2. 本地对象
   1. Array
   2. Number
   3. String
   4. Boolean
   5. Function
   6. RegExp
3. 宿主对象
   1. DOM
   2. BOM

### 三、Math对象

​		格式：Math.方法（参数）

1. 取绝对值
   1. Math.abs();
2. 取近似整数
   1. Math.round();四舍五入
   2. Math.floor();对数字向下取整（舍去小数）
   3. Math.ceil();对数字向上取整
3. 取最大值和最小值
   1. Math.max();
   2. Math.min();
4. 取随机数
   1. Math.rondom();0~1
   2. Math.

## 第二十课：字符串对象

### 一、属性

1. length

   计算字符串的长度，不区分中英文

2. constructor

   输出String的构造函数

### 二、方法

1. 获取类型
   1. charAt(num)
      1. 返回在指定位置的字符
      2. 越界返回空字符
   2. charCodeAt(num)
      1. 返回指定位置的字符的Unicode编码
   3. fromCharCode()
      1. 静态方法
      2. 使用String直接调用
      3. 接受一个或多个unicode值，返回一个或多个字符串
2. 查找类型
   1. indexOf()
      1. 返回某个指定的字符串在字符串中首次出现的位置
   2. lastIndexOf()
      1. 返回一个字符串中指定字符最后出现的位置
   3. match()
      1. 在字符串中检索指定的值，返回的值就是指定的类型（值）
      2. 需配合正则表达式使用
   4. search()
      1. 只能作用于正则表达式
   5. replace()
      1. 将字符串中的一些字符替换为另外一些字符
      2. 返回的是完整的字符串
3. 截取类型
   1. slice(start,end)
      1. 从指定的开始位置到指定的结束位置（不包括end位置）的所有字符
      2. 如果不指定结束位置则取到结尾
      3. 参数可以是负数，如果是负数，从-1开始指的是字符串结尾
   2. substring(start,end)
      1. 从指定的开始位置到指定的结束位置（不包括end位置）的所有字符
      2. 如果不指定结束位置则取到结尾
      3. 参数可以是负数，但是会自动转换为0
   3. substr(start,length)
      1. 从指定的位置开始取指定长度的字符串
      2. 如果没有指定长度，则取到结尾
4. 转换类型
   1. split("分割位置"，[指定的长度])
      1. 将一个字符串分割为数组
   2. toLowerCase()
      1. 用于把字符串转换为小写
   3. toUpperCase()
      1. 用于把字符串转换为大写
5. 样式类型
   1. fontcolor()
      1. 给字符串指定颜色
      2. 十六机制，英文，RGB
      3. 返回的是html代码
   2. fontsize()
      1. 指定字符串的大小（1~7）
      2. 返回的是html代码
6. 字符串填充（ES2017）
   1. padStart()----在字符串的开头进行填充
   2. padEnd()----在字符串的结尾进行填充

## 第二十一课：数组对象

### 一、属性

1. length

   设置或返回数组元素的数目

   ```js
   var ar = [1,2,3,4];
   alert(ar.length);
   alert(ar.length=5);
   alert(ar)//最后一个元素为undefined
   ```

2. constructor

   返回构造函数的一个引用

### 二、方法

1. 删除或添加类

   1. push(数组元素，数组元素......)
      1. 向数组的末尾添加新的元素
      2. 返回的是新数组的长度
      3. 可以一次添加多个元素
   2. unshift(数组元素.....)
      1. 向数组的开头加入新的元素
      2. 返回值是新数组的长度
      3. 可以一次添加多个元素
   3. pop()
      1. 删除数组的最后一个元素
      2. 返回删除的元素
   4. shift()
      1. 删除数组的第一个元素
      2. 返回删除的元素
   5. splice(index,数量，添加的元素.....)
      1. 万能的添加或删除函数
      2. index:从何处开始添加或删除，必须是数值类型（下标）
      3. 数量：规定了删除的个数，如果是0就不删除
      4. 添加的元素：可以当作替换的元素
      5. 如果有删除的元素，返回删除的元素

2. 数组的转换

   1. split()
   2. join(分隔符)
      1. 把数组元素按照指定分隔符组合成一个字符串
      2. 如果没有指定分隔符，默认使用逗号分隔
      3. 返回结果就是组合成的字符串

3. 数组的分割

   slice(start,end)
   1. 截取从指定开始位置到结束位置的元素
   2. 如果不指定结束位置，则取到结尾（数组的下标）
   3. 支持负数（-1）开始返回新数组

4. 排序

   1. 冒泡排序

   ```js
   for (var i = 0; i < ne.length; i++) {
   				for (var j = 0; j < ne.length - i; j++) {
   					if (ne[j] > ne[j + 1]) {
   						var a = ne[j];
   						ne[j] = ne[j + 1];
   						ne[j + 1] = a;
   				}
   		}
   }
   
   //封装冒泡排序
   function sort(){
       for(var i = 0;i < this.length;i++){
           for(var j = 0;j < this.length - i;j++){
               if(this[j]>this[j+1]){
                   var a = this[j];
                   this[j] = this[j + 1];
                   this[j + 1] = a;
               }
           }
       }
       return this;
   }
   Array.prototype.sort = sort;
   alert(arr.sort());
   ```

   1. sort()

      1. 对数组进行排序，如果没有参数，按照字母的编码进行排序
      2. 如果要按照其他的顺序来排序，要提供一个函数
      3. 提供两个参数a,b
      4. a<b，a在b的前面
      5. a<b，a在b的后面

      ```js
      //sort排序
      var ar = [1,23,4,23,12,4234,231,343]
      ar.sort(function (a,b){
          return a-b;
      })
      alert(ar);//从大到小排序
      
      ar.sort(function (a,b){
          return b-a;
      })
      alert(ar);//从小到大排序
      ```

5. 数组的连接

   concat()

   ​	连接两个或多个数组，并返回新的数组，但是对原数组没有任何影响

6. 自定义函数删除数组中重复元素

```js
//方式一
function deleteSameElement(){
    this.pickElement=function(arr){
        var newArr = new Array();
        for(var i = 0;i < arr.length;i++){
            if(!newArr.includes(arr[i])){
                newArr.push(arr[i]);
            }
        }
        return newArr;
    }
}

var arr = [1,2,3,4,5,6,7,1,2,3,4,5,6,7];
var deleteElement = new deleteSameElement();
alert(deleteElement.pickElement(arr);
      
//方式二
function deleteSameElement(){
    var newArr = new Array();
    for(var i = 0;i < this.length;i++){
        if(!newArr.includes(this[i])){
            newArr.push(this[i]);
        }
    }
    return newArr;
}
Array.pototype.sort = deleteSameElement;
var arr = [1,2,3,4,5,6,7,1,2,3,4];
alert(arr.sort());
```



## 第二十二课：JS浏览器对象模型BOM----window对象

window对象，是BOM中所有对象的核心

### 一、属性

1. 位置类型---获得浏览器的位置

   1. IE

   2. window.screenLeft

      可以获得浏览器距屏幕左上角的左边距

   3. window.screenTop

   4. window.screenRight

   5. window.screenBottom

   6. FF

   7. window.screenX

   8. window.screenY

2. 位置类型---获得浏览器的尺寸

   1. FF
   2. window.innerWidth----获得窗口的宽度
   3. window.innerheight----获得窗口的高度
   4. IE
   5. document.documentElement.clientHeight
   6. document.documentElement.clientWidth

3. 关系类型

   1. parent

      返回父窗口

   2. top

      返回顶层窗口

   3. self

      相当于window
      
   4. opener

      开启者

4. status

   设置窗口状态栏文本

### 二、方法

1. 窗体控制

   1. 对窗口的移动

   2. window.moveBy(x,y)

      相对于当前位置沿着x\y轴移动指定的像素，负数是反方向

   3. window.moveTo(x,y)

      相对于浏览器左上角沿着x\y轴移动指定的像素，负数是反方向

   4. 窗体尺寸的改变

      1. resizeBy(width,height)

         相对于当前窗口的大小，调整宽度和高度

      2. resizeTo(width,height)

         把窗体调整成指定的宽度和高度

2. 对窗体滚动条的控制

   1. scrollBy(x,y)

      相对于当前滚动条的位置移动的像素(前提是有滚动条)

   2. scrollTo(x,y)

      相对于当前窗口的高度和宽度移动到指定的像素

3. 时间间隔的函数

   1. setInterval("函数或者代码串"，指定的时间（毫秒）)

      按照指定的周期（毫秒）不断执行函数或代码串

      ```js
      var a = 0;
      setInterval(function(){
      	console.log(a);
      	a++;
      },1000)
      ```

      

   2. clearInterval(interval标识符)

      停止执行代码或函数

      ```html
      window.onload=function (){
      	var t = setInterval('alert("here")',3000);
      	var a = document.getElementById("stop");
      	a.onclick=function(){
      		clearInterval(t);
      	}
      }
      
      
      <body>
          <input type="button" id="stop" value="stop" />
      </body>
      ```

   3. setTimeout("函数或者代码串"，指定的时间（毫秒）)

      在指定的毫秒数后只执行一次函数或代码

   4. clearTimeout(timeout标识符)

      停止执行代码或函数

   ```js
   //模拟滚动条自动滚动，点击屏幕停止滚动
   window.onload = function() {
   	var t = setInterval(moves, 50);
   	function moves() {
   		scrollBy(0, 10);
   	}
   	document.body.onclick = function() {
   		clearInterval(t)
   	}
   }
   ```

4. 打开新的窗口

   open(url,name,features,replace)

   ​		通过脚本打开新的窗口

## 第二十三课：History、Location、Screen对象实例讲解

### 一、history对象

1. 包含浏览器访问过的url

   1. 属性

      length----返回浏览器历史记录的数量

      ```js
      history.length
      ```

   2. 方法

      1. back()----后退
      2. forward()----前进
      3. go(number)----如果参数是正数，那么就前进相应数目，如果是负数就反之，如果是0就是刷新

      ```html
      <!--history-->
      <script type="text/javascript">
      	window.onload = function() {
      		var first = document.getElementById("one");
      		first.onclick = function() {
      			history.forward();
      		}
      	}
      	alert(history.length);
      </script>
      
      <p>history1</p>
      <a href="history2.html">链接到2</a>
      <input type="button" name="" id="one" value="前进" />
      
      <!--history2-->
      <script type="text/javascript">
      	window.onload = function() {
      		var second = document.getElementById("two");
      		var third = document.getElementById("three");
      		second.onclick = function() {
      			history.back();
      		}
      		third.onclick=function(){
      			history.go(0);
      		}
      }
      		alert(history.length);
      </script>
      
      <p>history12</p>
      <a href="history.html">链接到1</a>
      <input type="button" name="" id="two" value="后退" />
      <input type="button" name="" id="three" value="刷新" />
      ```

### 二、Location对象

​		包含有当前url的相关信息

1. 属性

   1. href----设置或返回完整的url
   2. search----返回url?后面的查询部分

   ```html
   <!--只含有主要代码-->
   <!--第一个html文件：location.html-->
   <script>
   	alert(location.href="location2.html?1234");    
   </scripts>
   
   <!--第二个html文件：location2.html-->
   <script>
   	alert(location.search);
   </script>
   <p>here</p>
   
   ```

2. 方法

   1. assign----加载新的文档
   2. reload(boolean)----重新加载文档，当参数是true，任何时候都会重新加载，false的时候，只有在文档改变的时候才会加载，否则直接读取内存当中的数据
   3. replace----用新的文档代替当前的文档，没有历史记录

### 三、screen对象

​		记录客户端显示屏的信息

1. 属性
   1. availHeight----返回客户端屏幕有效高度
   2. availWidth----返回客户端屏幕有效宽度
   3. height----返回客户端屏幕高度
   4. width----返回客户端屏幕宽度

## 第二十四课：document对象详解

DOM----Document（html	xml）  Object  Modle

document对象是DOM的核心对象

作用：

1. 内容----innerHtml----获得html相应内容
2. 属性
3. 样式

进行调整



document对象

### 一、属性

1. title----返回或设置当前文档的标题
2. URL----返回当前文档的url
3. bgColor----设置文档的背景色
4. fgColor----设置文档的前景色（文字的颜色）

```js
document.title="";
document.URL;
document.bgColor="";
document.fgColor="";
```

### 二、方法

1. getElementById(idname)----返回拥有指定id的第一个对象的引用

2. getElementsByTagName(tagName)----返回带有指定标签名的对象的集合

   可以通过下标来访问这个集合

3. getElementsByName(name)----返回带有指定name名称的集合

   1. 是不兼容的，
   2. 主要适用于表单

4. write()

5. getElementsByClassName()----返回带有指定class指定名称的对象的集合

### 三、document对象的集合

1. all----所有元素的集合
2. form----返回对文档中所有form对象的引用
   1. 通过集合来访问相应的对象
   2. 通过下标的形式
   3. 通过name的形式
3. anchor----返回文档中所有anchor对象的引用
4. images----返回文档中所有image对象的引用
5. links----返回文档中所有area对象和links对象的引用

## 第二十五课：对文档对象的内容、属性、样式的操作

### 一、操作内容

1. innerHtml----用来设置或获取对象起始和元素标签内的内容（识别html标签）
2. innerText----用来设置或获取对象起始和元素标签内的内容
3. textContent----用来设置或获取对象起始和元素标签内的内容
4. outerHtml----用来设置或获取包括本对象在内起始和元素标签内的内容（识别html标签）
5. outerText----来设置或获取包括本对象在内起始和元素标签内的内容

### 二、操作属性

1. 直接操作
   1. 对象.属性
   2. 对象.属性=值
   3. 设置获取添加属性的值
2. as
   1. getAttribute("属性")----获取给定的属性的值
   2. setAttribute("属性"，"值")----设置或是添加属性

### 三、操作样式

1. 行内样式
   1. 对象.style.属性
   2. 对象.style.属性=值----设置、获取、添加样式
   3. 遇到属性用横线连接需要将横线去掉把第二个字母首字母大写
2. CSS层叠样式
   1. 通过id来更改样式
   2. 通过className来更改样式
      1. 适合批量更改样式
   3. 更改或者获取或者设置某个属性的值
      1. doucment.styleSheets[下标].rules[下标].style.属性
      2. doucment.styleSheets[下标].rules[下标].style.属性=值
         1. document.styleSheets----样式表的集合
         2. document.styleSheets[下标].rules----样式规则的列表
         3. document.styleSheets[下标].rules[下标].style----样式规则的集合
   4. 动态的添加删除CSS样式
      1. document.stySheets[下标].insertRule("选择器{属性:值}"，位置)
      2. document.stySheets[下标].deleteRule(位置)
      3. document.stySheets[下标].addRule("选择器"，"属性：值"，位置)
      4. document.stySheets[下标].removeRule(位置)
3. 行内样式和CSS层叠样式通用的方式
   1. 只能获取值不能修改
   2. 对象.currentStyle.属性----用来获得实际的样式属性
   3. getComputerStyle(对象,null)----用来获得实际的样式属性

## 第二十六课：对表单的操作

### 一、获得表单引用

1. 通过直接定位的方式来获取
   1. document.getElementById();
   2. document.getElementsByTagName();
   3. document.getElementsByName();
2. 通过集合的方式来获取引用
   1. document.forms[下标]
   2. document.forms["name"]
   3. document.forms.name
3. 通过name直接获取，只适用于表单
   1. document.name

### 二、如何获得表单元素的引用

1. 直接获取

   1. document.getElementById();
   2. document.getElementsByTagName();
   3. document.getElementsByName();

2. 通过集合来获取

   1. 表单对象.elements----获得表单里面所有元素的集合

   ```js
   document.myform.elements.length
   ```

   2. 表单对象.elements[下标]
   3. 表单对象.elements.name
   4. 表单对象.elements["name"]

3. 直接通过name的形式

   表单对象.name

### 三、表单元素共同的属性和方法

1. 获取表单元素的值

   1. 表单元素对象.value----获取或是设置值

2. 属性

   1. disabled----获取或设置表单控件是否禁用--true--false
   2. form----指向包含本元素的引用

3. 方法

   1. blur----失去焦点
   2. focus----获得焦点

   ```js
   document.forms[].elements.name.focus();
   ```

### 四、文本框

\<input type="text">----操作文本域的值，value----获取或设置值

### 五、单选按钮

checked----返回或者设置单选的选中状态

只有一个值----checked

value----属性，获取选中的值，必须先判断选中状态

### 六、多选按钮

checked----返回或者设置单选的选中状态

只有一个值----checked

value----属性，获取选中的值，必须先判断选中状态

### 七、下拉框

selected----设置或者返回下拉框的选中状态

selectedIndex----设置或返回下拉框被选中的索引号

### 八、文本区域

\<textarea>\</textarea>

value----操作值

### 九、验证表单

1. 事件
   1. onsubmit----当表单提交时触发的事件
   2. onblur
   3. onfocus
   4. onchange
2. return false
   1. 阻止事件的默认行为（适用于所有事件）

### 十、提交方法

表单对象.submit()

## 第二十七课：节点属性

DOM，HTML文档中的每一个成分都是一个节点

DOM规定：

1. 整个文档是一个文档节点
2. 每个HTML标签是一个元素节点
3. 包含在HTML元素中的文本是文本节点
4. 每一个HTML属性是一个属性节点
5. 注释属于注释节点

### 一、如何获得节点引用

1. 旧的获取节点引用方式
   1. document.getElementById();
   2. document.getElementsByTagName();
   3. document.getElementsByName();
   4. 浪费内存；逻辑性不强
2. 通过节点关系属性获得节点的引用
   1. 对象.parentNode----获得父节点的引用
   2. 对象.childNode----获得子节点的集合
   3. 对象.firstChild----获得第一个子节点
   4. 对象.lastChild----获得最后一个子节点
   5. 对象.nextSibling----获得下一个兄弟节点的引用
   6. 对象.previousSibling----获得上一个兄弟节点的引用
   7. 兼容型不好

### 二、节点的信息（属性）

nodeType

nodeName

nodeValue

1. 节点分类：元素节点----属性节点----文本节点----注释节点----文档节点
2. 节点类型：      1      ----      2      ----       3      ----      8      ----      9
3. 节点名字： 标签名  ----  属性名  ----   #next  ----#comment----#document
4. 节点值：       null    ----   属性值 ----    文本    ----注释的文字---- null

## 第二十八课：节点的增删改查

### 一、创建节点

1. 创建元素节点
   1. document.createElement("元素标签")
2. 创建属性节点
   1. document.createAttribute("属性名");
   2. 对象.属性="属性值"
   3. 对象.setAttribute(属性名，属性值)
   4. 对象.getAttribute(属性名，属性值)
3. 创建文本节点
   1. 对象.innerHTML=""
   2. document.createTextNode("文本")

### 二、追加到页面当中

1. 父对象.appendChild("要追加的对象")----追加到最后
2. 父对象.insertBefore(要插入的对象，之前的对象)----插入到后面

### 三、修改（替换）节点

父对象.replaceChild("要修改的对象","被修改的对象");

### 四、删除节点

父对象.removeChild(删除的对象)

如果确定要删除节点，最好也清空内存

对象=null

## 第二十九课：事件基础和事件绑定

### 一、事件驱动

1. 事件

   JavaScript侦测到的用户的操作或是页面的一些行为

2. 事件源

   1. 引发事件的元素
   2. 发生在谁的身上

3. 事件处理程序

   1. 对事件处理的程序或是函数
   2. 发生了什么事

### 二、事件的分类

1. 鼠标事件
   1. onclick
   2. ondbclick
   3. onmouseup
   4. onmousemove
   5. onmouseover
   6. onmouseout
2. 键盘事件
   1. onkeyup
   2. onkeyown
   3. onkeypress
3. 表单事件
   1. onsubmit
   2. onblur
   3. onfocus
   4. onchange
4. 页面事件
   1. onload
   2. onunload
   3. onbeforeunload

### 三、如何绑定事件

1. 在脚本中绑定
2. 直接在HTML元素绑定
3. \<script for="指定的元素" event="事件">事件处理程序\</script>

### 四、同一个事件绑定多个事件处理程序

1. 对象.attachEvent("事件（on）"，"处理程序")----添加
2. 对象.detachEvent("事件（on）"，"处理程序")----删除
3. 对象.addEventListener("事件"，"处理程序"，布尔值)----添加
4. 对象.removeEventlistener("事件"，"处理程序"，布尔值)----删除

## 第三十课：事件对象

### 一、事件对象

用来记录一些事件发生时的相关信息的对象

1. 只有当事件发生的时候才产生，只能在处理函数内部访问
2. 处理函数运行结束后自动销毁

### 二、如何获取事件

1. IE：window.event
2. FF：对象.on事件=function (e){}

### 三、事件对象的属性

1. 关于鼠标事件的事件对象

   1. 相对于浏览器位置的

      1. clientX----鼠标事件发生的时候，鼠标相对于浏览器x轴的位置
      2. clientY----鼠标事件发生的时候，鼠标相对于浏览器y轴的位置

      ```html
      <div id="one" style="width: 200px;height: 200px;border: 1px solid red;">
      </div>
      <script type="text/javascript">
      	var div1 = document.getElementById("one");
      	document.onmousemove = function(e){
      		var ev = e||window.event;
      		var cx = ev.clientX;
      		var cy = ev.clientY;
      		div1.innerHTML = "cx="+cx+"---cy="+cy;
      	}
      </script>
      ```

   2. 相对于屏幕位置的

      1. screenX----鼠标事件发生的时候，鼠标相对于屏幕x轴的位置
      2. screenY----鼠标事件发生的时候，鼠标相对于屏幕y轴的位置

   3. 相对于事件源的位置

      1. IE：
      2. offsetX----鼠标事件发生的时候，鼠标相对于事件源x轴的位置
      3. offsetY----鼠标事件发生的时候，鼠标相对于事件源y轴的位置
      4. FF:
      5. layerX----鼠标事件发生的时候，鼠标相对于事件源x轴的位置
      6. laterY----鼠标事件发生的时候，鼠标相对于事件源y轴的位置

2. 关于键盘事件的事件对象

   1. keyCode----获得键盘码
   2. altKey----判断alt键是否被按下，按下是true，没有是false
   3. ctrlKey----判断ctrl键是否被按下，按下是true，没有是false
   4. shiftKey----判断shift键是否被按下，按下是true，没有是false
   5. type----用来检测事件的类型，主要是用于对个事件通用一个事件处理程序的时候

## 第三十一课：事件流讲解和应用

当页面元素触发事件的时候，该元素的容器以及整个页面都会按照待定的顺序响应该元素的触发事件，时间传播的顺序叫做时间流程

### 一、事件流的分类

1. 冒泡性事件
   1. 由明确的事件源到最不确定的事件源依次向上触发
2. 捕获型事件
   1. 由不确定的事件源到明确的事件源依次向下触发

### 二、阻止事件流

1. IE
2. 事件对象.cancelBubble=true;
3. FF
4. 事件对象.stopPropagation();

### 三、目标事件源的对象

1. IE
2. 事件对象.srcElement
3. FF
4. 事件对象.target

## 第三十二课：日期对象

### 一、创建日期对象

1. 当前时间：var a = new Date();
2. 指定的时间：var a = new Date("hour/min/sec mon/day/year");
3. var a = new Date(year,mon,day,hour,min,sec);

### 二、方法

1. 获取类型
   1. 获取日期信息的方法
   2. getDate()----从Date对象返回一个月中的某一天1~31
   3. getDay()----从Date对象返回一周中的某一天0~6
   4. getMonth()----从Date对象返回月份0~11
   5. getFullYear()----从Date对象以四位数字返回年份
   6. getYear()----使用getFulllYear()代替
   7. getHours()----返回Date对象的小时0~23
   8. getMinutes()----返回Date对象的分钟0~59
   9. getSeconds()----返回Date对象的秒数0~59
   10. getMilliseconds()----返回Date对象的毫秒0~999
   11. getTime()----返回1970年1月1日至今的毫秒数
   12. getTimezoneOffset()----返回本地时间与格林尼治标准时间的分钟差
2. 设置类型
   1. setDate()----设置Date对象中月的某一天1~31
   2. setMonth()----设置Date对象中月份0~11
   3. setFullYear()----设置Date对象中的年份四位数字
   4. setYear()----使用setFullYear代替
   5. setHours----设置Date对象中的分钟0~23
   6. setMinutes()----设置Date对象中的分钟0~59
   7. setSeconds()----设置Date对象中的秒钟0~59
   8. setMilliseconds()----设置Date对象中的毫秒数0~999
   9. setTime()----以毫秒设置Date对象
   10. setUTCDate()----根据世界时设置Date对象中月份的一天1~31
   11. setUTCMonth()----根据世界时设置Date对象中的月份0~11
   12. setUTCFullYear()----根据世界时设置Date对象中的年份（四位数字）
   13. setUTCHours()----根据世界时设置Date对象中的小时0~23
   14. setUTCMinutes()----根据世界时设置Date对象中的分钟0~59
   15. setUTCSeconds()----根据世界时设置Date对象中的秒钟0~59
   16. setUTCMilliseconds()----根据世界时设置Date对象中的毫秒数0~999

 ## 1.正则表达式

### 一、语法

		1. 直接量语法----/pattern/modifiers
  		2. 创建对象----new RegExp(pattern,modifiers);

### 二、修饰符

1. i----执行大小写不敏感的匹配
2. g----执行全局匹配（查找所有匹配而非在找到第一个后停止）
3. m----执行多行匹配

### 三、模式

1. 括号

   1. [abc]----查找方括号内的任何字符
   2. [0-9]----查找任何从0至9的数字
   3. (x|y)----查找有|分隔的任何选项

   ```js
   
   var str = "Is this all there is?";
   var patt1 = /[h]/g;
   var result = str.match(patt1);//result="h,h"
   
   
   var str = "123456789";
   var patt2 = /[1~4]/g;
   var result = str.match(patt2);//result="1,2,3,4"
   
   
   var str = "re,green,red,green,gren,gr,blue,yellow";
   var patt3 = /(red|green)/g;
   var result = str.match(patt3);//result="green,red,green"
   ```

2. 元字符（Metacharacter）

   1. \d----查找数字
   2. \s----查找空白字符
   3. \b----匹配单词边界
   4. \uxxxx----查找以十六进制数xxxx规定的Unicode字符

   ```js
   var str = "given 100%";
   var patt4 = /\d/g;
   var result = str .match(patt4);//result="1,0,0"
   
   
   var str = "Is this all there is?";
   var patt5 = /\s/g;
   var result = str.match(patt5);//result=,,,
   
   
   var str = "visit w3school";
   var patt6 = /\bw3/g;
   var result = str.match(patt6);//result="w3"
   
   
   var str = "visit W3school";
   var patt7 = /\u0057/g;
   var result = str.match(patt7);//result="W"
   ```

3. 定义量词（Quantifiers）

   1. n+----匹配任何包含至少一个n的字符串
   2. n*----匹配任何包含零个或多个n的字符串
   3. n?----匹配任何包含零个或一个n的字符串

   ```js
   var str = "Hellooo World! Hello W3school!";
   var patt8 = /o+/g;
   var result = str.match(patt8);//result="ooo,o,o,oo"
   
   
   var str = "Hellooo World! Hello W3school!";
   var patt9 = /lo*/g;
   var result = str.match(patt9);//result="l,looo,l,l,lo,l"
   
   
   var str = "1,100,or,1000?";
   var patt10 = /10?/g;
   var result = str.match(patt10);//result="1,10,10"
   ```

### 四、方法

1. test()

   test()是一个正则表达式方法，可用来对指定的字符串进行搜索指定内容，返回true或false

```js
var patt = /e/;
patt.test("The best things in life are free.")//返回true

//等价于
/e/.test("The best things in life are free.")//返回true
```

2. exec()

   通过指定的模式搜索字符串，并返回已找到的文本，如果未匹配返回null

   ```js
   /e/.test("The best things in life are free.")//返回e
   ```

   

## 2.JS错误

try----测试代码块中的错误

catch----处理错误

throw----创建自定义错误

finally----在try和catch后，无论结果如何，执行代码

### 一、try...catch

语法：try{}catch{}finally{}

```js
try{
    供测试的代码
}catch(err){
    处理错误的代码
}
```

1. err属性----name----设置或返回错误名

   1. EvalError----已在eval()函数中发生错误
      1. 指示eval()函数中的错误
      2. 请使用SyntaxError代替
   2. RangeError----已发生超出数字范围的错误

   ```html
   <p id="demo"></p>
   <script>
       var num = 1;
       try{
           num.toPrecision(500);//参数1~21
       }catch(e){
           document.getElementById("demo").innerHTML=e.name;
       }	
   </script>
   ```

   3. ReferenceError----已发生非法引用

   ```html
   <p id="demo"></p>
   <script>
   var x = 0;
   try{
   	x = y+2;
   }catch(e){
   	document.getElementById("demo").innerHTML=e.name;
   }
   </script>
   ```

   

   4. SyntaxError----已发生语法错误

   ```html
   <p id="demo"></p>
   <script type="text/javascript">
   	try{
   		eval("alert('asd)");
   	}catch(e){
   		document.getElementById("demo").innerHTML=e.name;
   	}
   </script>
   ```

   

   5. TypeError----已发生类型错误

   ```html
   <p id="demo"></p>
   <script type="text/javascript">
   	var x = 1;
   	try{
   		x.toUpperCase();
   	}catch(e){
   		document.getElementById("demo").innerHTML=e.name;
   	}
   </script>	
   ```

   

   6. URLError----在encodeURL()中已发生的错误

   ```html
   <p id="demo"></p>
   <script type="text/javascript">
   	var x = 1;
   	try{
   		decodeURI("%%%");
   	}catch(e){
   		document.getElementById("demo").innerHTML=e.name;
   	}
   </script>
   ```

   

2. err属性----message----设置或返回错误信息（一条字符串）

### 二、throw

创建自定义错误，可以抛出字符串、数字、布尔、对象

throw和trycatch一起使用可以控制程序流并生成自定义错误信息

### 三、finally

语法：try{}catch(err){}finally{}

```js
try{
    //供测试的代码
}catch(err){
    //处理的代码
}finally{
    //无论结果如何都会执行的代码
}
```





### HTML验证

```js
<p>请输入5到10之间的数字</p>
<input type="text" id="num">
<button type="button" onclick="myFunction()">检测输入</button>
<p id="demo"></p>

<script type="text/javascript">
	function myFunction() {
		var message, x;
		message = document.getElementById("demo");
		message.innerHTML = "";
		x = document.getElementById("num").value;
		try {
			if (x == "") throw "是空的";
			if (isNaN(x)) throw "不是数字";
			x = Number(x);
			if (x < 5) throw "太小";
			if (x > 10) throw "太大";
		} catch (e) {
			message.innerHTML = "输入：" + e;
		}finally{
            document.getElementById("num").value="";
        }
	}
```



## 3.Hoisting

### 一、概念

​		提升是js将所有声明移至作用域顶部的默认行为（提升到当前脚本或当前函数的顶部）

### 二、例外

1. let
2. const
3. 不会被提升

### 三、注意

1. js初始化不会被提升

```js
var x = 5;
var y = 7;
elem = document.getElementById("demo");
elem.innerHTML=x + " " + y;//5 7

var x = 5;
elem = document.getElementById("demo");
elem.innerHTML = x + " " + y;//5 undefined
var y = 7;
```



## 4.严格模式

### 一、概念

use strict : 定义js代码应该以”严格模式“执行

指令

js1.8.5新加

是一段文字表达式，不算语句



### 二、声明

1. 通过在脚本或函数的开头添加”use strict;“来声明严格模式

```html
<script>
    "use strict;"
    x = 3.14;
    //在控制台中报错
</script>
```

2. 在函数中声明严格模式，拥有局部作用域（只有函数中的代码以严格模式执行）
3. 只能在的脚本或函数的开头被识别

### 三、使用的原因

1. 普通js中向不可写属性赋值，开发者不会得到任何错误反馈
2. 在严格模式下，向不可写的、只能读取的、不存在的属性赋值，或者像不存在的变量或对象赋值，将抛出错误

### 四、不允许的事项

1. 在不声明变量的情况下使用变量是不允许的
2. 在不声明对象的情况下使用对象是不允许的
3. 删除变量（或对象）是不允许的
4. 删除函数是不允许的
5. 重复参数名是不允许的
6. 八进制文本是不允许的
7. 转义字符是不允许的
8. 写入只读属性是不允许的
9. 写入只能获取的属性是不允许的
10. 删除不可删除的属性是不允许的
11. 字符串”eval“不可用作变量
12. 字符串”arguments“不可用做变量
13. with语句是不允许的
14. 出于安全考虑，不允许eval()在其被调用的作用域中创建变量
15. 严格模式下不允许使用保留字（implements,interface,let,package,private,protected,public,static,yield）



## 5.this关键字

### 一、概念

this关键字指的是它所属的对象

### 二、取值

1. 在方法中，this指的是所有者对象

```js
var person={
    firstName:"Bill",
    lastName:"Gates",
    id:678,
    fullName:function(){
        return this.firstName+ " " +this.lastName;//这里的this指的就是person对象，相当于自己调用自己的属性
    }
}
```



2. 单独的情况下，this指的是全局对象（包括严格模式下）

```js
var x = this;
document.getElementById("demo").innerHTML=x;//[object Window]
```



3. 在函数中，this指的是全局对象

4. 在函数中，严格模式下，this是undefined

5. 在事件中，this指的是接收事件的元素



### 三、显示函数绑定

1. call()

```js
var person1 = function(){
    fullName:function(){
        return this.firstName + " " + this.lastName;
    }
}
var person2 = function(){
    fisrtName:"Bill",
    lastName:"Gates"
}
person1.fullName().call(person2);//返回 Bill Gates
```



2. apply()





## 6.箭头函数

### 一、语法

var hello = (参数) => {//函数体}







## 7.JS类

JS类不是对象，指示JS对象的模板

语法：使用class定义

始终添加constructor()方法

```js
class ClassName{
    constructor(){}
}
```



构造方法特性：

1. 必须拥有确切名称的“构造函数"
2. 创建新对象是自动执行
3. 用来初始化对象属性
4. 如果未定义构造函数方法，JS会添加空的构造函数方法

class方法：

类方法的创建



## 8.JSON

JSON是存储和传输数据的格式

JSON经常在数据从服务器发送到网页时使用

JSON===JavaScript Object Notation

JSON是轻量级的数据交换格式

JSON独立于语言，JSON的格式是纯文本的，读取和生成JSON数据的代码可以在任何编程语言编写

JSON是”自描述的“且易于理解 





JSON语法规则

1. 数据是名称/值对
2. 数据由逗号分隔
3. 花括号保存对象
4. 方括号保存数组

```json
{
    "emploees":[
        {"fisrtName":"Bill","lastName":"Gates"}
        {"fisrtName":"Steve","lastName":"Jobs"}
        {"fisrtName":"Alan","lastName":"Turing"}
    ]
}
```

JSON名称需要双引号



JSON中数组于对象可以相互嵌套

把JSON文本转换为JavaScript对象

```js


var text = "{
    "emploees":[
        {"fisrtName":"Bill","lastName":"Gates"}
        {"fisrtName":"Steve","lastName":"Jobs"}
        {"fisrtName":"Alan","lastName":"Turing"}
    ]
}"

var obj = JSON.parse(text);//获得js对象
```

var obj = JSON.parse(text);



## 9.调式

debugger关键词

cosole.log()



## 10.样式指南

代码约定指的是编程的演示指导方针

1. 变量和函数的命名和声明规则
2. 使用空格、缩进和注释的规则
3. 编程习惯和准则

代码约定确保质量：

1. 改善代码可读性
2. 提升代码可维护性

参考规则：

1. 变量名----驼峰式大小写；字母开头
2. 运算符周围以及逗号之后添加空格
3. 代码缩进----使用4个空格，尽量不使用tab键
4. 语句规则
   1. 简单语句规则----始终以分号结束单条语句
   2. 复杂语句规则
      1. 第一行的结尾处写开括号
      2. 在开括号前使用一个空格
      3. 在新行上写闭括号，不带前导空格
      4. 请不要使用分号来结束复杂语句
5. 对象规则
   1. 把开括号于对象名放在同一行
   2. 在每个属性与其值之间是哦那个冒号加一个空格
   3. 不要在最后一个属性值的后面写逗号
   4. 在新行上写闭括号，不带前导空格
   5. 始终以分号结束对象定义
   6. 可以对短对象在一行中进行压缩，只在属性之间使用空格
6. 行长度小于80，换行位置是运算符和逗号之后





替代

1. {}替代new Object()
2. ”“替代new String()
3. 0替代new Number()
4. false替代new Boolean()
5. []替代new Array()
6. /()/替代new RegExp()
7. fucntion(){}替代new Function()



字符串减去字符串会得到NaN



===会强制对值和类型进行强制比较

==比较运算符总会在比较之前进行类型转换（以匹配类型）





## JS性能

1. 减少循环中的活动，将一些已知的变量值在循环体外定义
2. 减少DOM访问，多次访问可以将它作为本地变量来使用
3. 缩减DOM规模
4. 避免不必要的变量
5. 延迟JS加载，把脚本放在页面底部，使浏览器数显加载页面
6. 避免使用with





## AJAX

###  使用方式

1.创建XMLHttpRequest对象
2.配置请求信息（.open(请求方式，请求地址，是否异步)）
请求方式：GET POST PUT DELETE...
请求地址：后端API接口
是否异步：默认true，false同步
3.发送请求（.send()）
4.接收响应
onload事件
onreadystatechange事件
readystate:0(请求未初始化)1(服务器连接已建立)2(请求已接收)3(请求已处理)4(请求已完成且响应已就绪)
status:200(ok)404(未找到页面)
5.数据
responseText
responseXML

```js
var xhr = new XMLHttpRequest();
xhr.open("GET","http://poetry.apiopen.top/sentences");
xhr.send();
//xhr.setRequestHeader("Content-type","application/x-www-form-urlencoded");POST使用该语法
xhr.onreadystatechange = function(){
							if(xhr.reaystate==4&&xhr.status==200){
								console.log(xhr.responseText);
							}
						}
```




JSON
语法：key : value


JSON.parse()——把json格式的字符串转换成js的数组对象
JSON.stringify()——把js的数组或字符串转换成JSON格式字符串



消息结构

状态码

建立连接——三次握手

断开连接——四次挥手







## JS额外笔记

基于对象的编程语言
所有对象已经由浏览器设计好，直接使用


prototype属于对原生功能拓展



事件处理是整个JS核心操作


window.freeze()冻结变量或对象，无法对其进行修改



鼠标事件：
onmousedown——鼠标按下触发
onmousemove——鼠标鼠标移动时触发
onmouseout——鼠标退出范围触发
onmouseover——鼠标进入范围触发
onmouseup——鼠标抬起触发

onclick——点击
onfocus——得到焦点
onblur——失去焦点
ondbclick——双击






JS中每一个元素都是一个对象




\<tr onmoousedown="functionName(this,attr)">\</tr>//this指的是当前对象



所有的事件都要绑定在一个元素（对象）上


每一种事件都一定要捆绑一个函数进行事件的处理


id是整个JS的操作核心所在，必须存在




addEventListener(事件名称，处理函数，触发时机)
事件名称：
mouseover
mousedown
mouseout
mouseup
mousemove

click
focus
blur


onkeydown
onkeyup
pnkeypress

整个JS时间的处理分为两个部分：
事件的冒泡过程
事件的触发过程
触发时机设置成false，表示在是假的触发过程进行处理，阻止事件冒泡


innerHTML可以添加html代码



操作脚标


时间发生器
setTimeout(函数，毫秒)，定期执行操作


表单控件的name和id要保持一致




一定要定义正则的开始与结束，正则表达式不需要转义

/^正则$/.test(要检测的数据)


使用正则表达式来验证表单信息



表单验证流程：
由用户输入表单内容
如果输入合法则提交
如果输入不合法则不允许提交


如果要想针对表单验证进行拦截，必须使用onsubmit事件，实在form元素里面定义的，表示进行表单提交时触发，如果需要对表单进行拦截，那么就在onsubmit处理函数上返回false，如果要正常执行，则返回true即可




return 函数返回值（boolean），false则停止执行，true则继续执行


尽量不使用弹窗来提示


最好的验证方式是文本框失去焦点







文本验证模型


<body>部分
<form action="formTEST.html" method="post" onsubmit="return validataResult()">
<!--return表示接受函数的结果，用于判断是否进行提交,返回true则提交，返回false则不提交-->
请输入账号：
<input type="text" name="acount" id="acount" value="" class="init" onblur="validata()"/>
<span id="alertWords"></span><br>
<button type="submit">提交</button>
</form>



<script>部分
<script type="text/javascript">
	function validata() {
		var acount = document.getElementById("acount");
		var acountNum = acount.value;
		var alertWords = document.getElementById("alertWords");
		if (/[0-9]/.test(acountNum)) {
			acount.className = "right";
			alertWords.innerHTML = "<font color='green'>验证成功</font>"
			return true;
		} else {
			acount.className = "wrong";
			alertWords.innerHTML = "<font color='red'>验证失败</font>"
			return false;
		}
	}
	function validataResult() {
		return validata();
	}
</script>


<style>部分
<style type="text/css">
            .init {
                background: #f5f5f5;
                font-weight: bold;
                color: #000000;
            }
            .wrong {
                background: #f5f5f5;
                font-weight: bold;
                border: 1px solid #ff0000;
                color: #000000;
            .right {
            background-color: #f5f5f5;
            font-weight: bold;
            color: #000000;
            border: 1px solid #00ff00;
        }
 </style>









密码验证





```js
<style type="text/css">
            .init {
                background: #f5f5f5;
                font-weight: bold;
                color: #000000;
            }
            .wrong {
            background: #f5f5f5;
            font-weight: bold;
            border: 1px solid #ff0000;
            color: #000000;
        }
        .right {
        background-color: #f5f5f5;
        font-weight: bold;
        color: #000000;
        border: 1px solid #00ff00;
    }
</style>
```

```js
<script type="text/javascript">
	function validataEmpty(element) { //公共函数
		var objElement = document.getElementById(element);
		var msgElement = document.getElementById(element + "Msg");
		if (objElement.value != "") {
			objElement.className = "right";
			msgElement.innerHTML = "<font color='green'>输入内容正确</font>"
			return true;
		} else {
			objElement.className = "wrong";
			msgElement.innerHTML = "<font color='red'>输入内容错误</font>"
			return false;
		}
	}	
	function validataRepeat(srcName, desName) {
		var srcElement = document.getElementById(srcName);
		var desElement = document.getElementById(desName);
		var msgElement = document.getElementById(desName + "Msg");
		if (srcElement.value == desElement.value) {
			desElement.className = "right";
			msgElement.innerHTML = "<font color='green'>密码验证成功</font>";
			return true;
		} else {
			desElement.className = "wrong";
			msgElement.innerHTML = "<font color='red'>密码验证错误</font>"
			return false;
		}
	}
	function validPwd() {
		return validataEmpty("pwd");
	}
	function validConf() {
		if (validataEmpty("conf")) {
			return validataRepeat("pwd", "conf");
		}
		return false;
	}          
	window.onload = function(){
		document.getElementById("pwd").addEventListener("blur",validPwd,false);
		document.getElementById("conf").addEventListener("blur",validConf,false);
	}
</script>







<body>
	输入密码：<input type="password" name="pwd" id="pwd" class="init" value="">
	<span id="pwdMsg"></span><br>
	确认密码：<input type="password" name="conf" id="conf" class="init" value="" />
	<span id="confMsg"></span><br>
</body>

```





最好的代码就是互不干涉，每个文件独立存在





单选钮
如果出现多个id和name，JS会将它们放在一个对象数组中，使用document.getElementById()取得的话，只是数组的第一个元素，想取得所有的对象要使用document.all()来完成，返回的是对象数组



要判断某个选项被选中，只能通过“checked”实现



按钮验证
html部分

```html
    <input type="radio" name="sex" id="sex" value="男" checked="checked"/>男
    <input type="radio" name="sex" id="sex" value="女" />女
    <button type="button" onclick="getsex()">提交</button>
```


JS部分

```js
        function getsex(){
            var sexa = document.all("sex");
            if(sexa[0].checked){
                alert("性别是："+sexa[0].value);
            }
            if(sexa[1].checked){
                alert("性别是："+sexa[1].value);
            }
        }
```








复选框的全选功能主要是靠checked属性来实现的
        

```html
   html部分
        <input type="checkbox" name="inst" id="inst" value="1" />1 <br>
        <input type="checkbox" name="inst" id="inst" value="2" />2<br>
        <input type="checkbox" name="inst" id="inst" value="3" />3<br>
        <input type="checkbox" name="inst" id="inst" value="4" />4<br>
        <input type="checkbox" name="inst" id="inst" value="5" />5<br>
        <input type="checkbox" name="inst" id="inst" value="6" />6<br>
        <input type="checkbox" name="inst" id="inst" value="7" />7<br>
        <input type="checkbox" name="inst" id="inst" value="8" />8 <br>
        <input type="checkbox" name="inst" id="inst" value="9" />9 <br>
        <input type="checkbox" name="inst" id="inst" value="0" />0 <br>
        <input type="checkbox" name="inst" id="inst" value="11" />11 <br>
   
  
   <input type="checkbox" name="all" id="all" value="全选" onclick="seleteAll()"/>全选
    <button type="button" onclick="showinst()">显示</button>
```

JS部分
            function showinst() {
                var inst = document.all("inst");
                var d = "选中的是："
                for (var x = 0; x < inst.length; x++) {
                    if (inst[x].checked) {
                        d += inst[x].value+" ";
                    }
                }
                alert(d);
            }
            function seleteAll(){
                var geta = document.all("inst");
                for(var s = 0;s<geta.length;s++){
                    geta[s].checked = document.getElementById("all").checked;
                }
            }


下拉列表框进行表单交互使用的事件是onchange事件，表示下拉内容发生改变


JS部分

```js
        function getCity(city){
            alert("选择的是：" + city);
        }
```





html部分

```html
    请选择：
    <select name="city" id="city" onchange="getCity(this.value)">
        <option value="bj" selected>bj</option>
        <option value="sh">sh</option>
        <option value="sz">sz</option>
        <option value="gd">gd</option>
    </select>
```





文本域主要是用来进行大文本信息的输入操作使用的，但是在文本域上同样可以使用一系列的操作事件



所有的按钮都有一个disabled属性





window下有一个confirm()函数，返回boolean值，提供一个确认框



window.open()在现有的窗口上打开另一个窗口，即弹窗

window.close()关闭打开的窗口


重定向：window.location


JS部分

function fun(url){
	window.location = url;
}


body部分



```html
<select id="url" name="url" onchange="fun(this.value)">
	<option value="..."></option>
	<option value="..."></option>
</select>
```

利用重定向类似于超链接，地址栏会发生改变





每一个html元素都是JS的一个对象


表单利用表格布局



对于表单的验证可以使用onblur事件来触发验证函数




正则表达式格式：/^ $/



为表单控件的单个元素添加验证时需要最后为表单添加整体验证功能，拦截验证使用onsubmit事件进行处理，编写一个综合的验证代码函数





判断代码是好坏的标准：代码是否足够简单，能否用少的代码实现更多的功能
可以创建一个保存所有的通用操作函数



对于日期的验证，可以使用日期组件来验证









## CSS属性额外笔记

css属性：
1 placeHolder--输入框提示文字，浅色，失去焦点同时输入框为空时会显示
2 z-index--设置元素堆叠顺序，值越高越靠前
3 rgba(0,0,0,0.4)--最后一个设置透明度（0~1）
4 cursor--设置鼠标到达时鼠标的样式，有这几种：pointer-help--grab--wait--crosshair--not-allowed--zoom-in--zoom-out
5 opacity--css中设置透明度
6 input[]--[]内是类型，type，为指定类型的输入框设置属性
7 box-sizing--默认content-box，元素的宽度设置为100px时，如果添加元素的边框和内边距，会让整个元素的宽度变大；border-box则会将边框和内边距算在元素宽度内
8 button--3种方式实现button标签的跳转：1.添加onclick事件，onclick="window.location.href='#'";2.在button外套一个a标签；3.使用JS







## 浏览器存储数据对象

localStorage：永久存储（硬盘中）

sessionStorage：会话缓存（内存）

```js
//存数据
localStorage.setItem(属性,值);
//查数据
loaclStorage.getItem(属性);
//删除数据
loaclStorage.removeItem(属性)
//清空
localStorage.clear();
//sessionStorage用法一样，但这个是局部使用
//localStorage则是全局
```







## 闭包

延长变量的作用范围









































