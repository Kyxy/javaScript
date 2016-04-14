## JavaScript入门

##### 学习原因

1. 所有浏览器都支持JavaScript；
2. JavaScript可以让网页呈现各种动态效果。
3. JavaScript简单易学。

##### 网页中插入JavaScript代码

在网页中嵌入html代码，只需要在`head`标签中插入`<script>···</script>`，将JavaScript代码写在`script`标签中即可。

```javascript
<script type="text/javascript">
  document.write("hello world!");
</script>
```

##### 引用独立JS外部文件

可以使用`script`标签将JavaScript代码嵌入html文件中，也可以单独创建JavaScript代码，保存在后缀为`.js`的文件中，将html文件和JS代码分开。在JS文件中不需要`<script></script>`，直接写入JavaScript代码即可。

在html文件中嵌入JS代码：

```javascript
<script src=""script.js></script>
```

##### JavaScript在html文件中的位置

JavaScript代码可以放在html文件中的任何位置（解释型语言）。但是习惯上放在网页的`head`部分或者`body`部分。

**放在`head`**：浏览器解析网页时先执行JavaScript代码，再解析页面的其余部分；

```javascript
<head>
    <script type="text/javascript">
            //JavaScript代码
    </script>
  
  	<script src="code.js"></script>
</head>
```

**放在`body`**：JavaScript代码会在浏览器解析到该语句时执行（浏览器从上至下解析）。

```javascript
<body>
  	<script type="text/javascript">
            //JavaScript代码
    </script>
</body>
```

注：JavaScript作为脚本语言可以放在html页面的任何位置，但是浏览器解释html是有先后顺序的，所以前面的JavaScript代码先执行。进行**页面初始化**的js必须放在`head`中，初始化都要求提前执行；通过事件调用的function对位置没有要求。

##### 语句和符号

JavaScript语句是发送给浏览器的命令，告诉浏览器要做的的事情。

语法：

1. 每句JavaScript代码由`语句;`组成；

2. 语句表示浏览器要执行的命令，分号标识一个语句的结束（分号在英文状态下输入）。

   ```javascript
   <script type="text/javascript">
      document.write("I");
      document.write("love");
      document.write("JavaScript");
   </script>
   ```

##### 注释

注释的作用是提高代码可读性，帮助自己和别人阅读和理解你所编写的JavaScript代码，注释 内容不会显示在网页上。

**单行注释`//`**：

```javascript
<script type="text/javascript">
  document.write("单行注释使用'//'");  // 我是注释，该语句功能在网页中输出内容
</script>
```

**多行注释`/*···*/`**：

```javascript
<script type="text/javascript">
   document.write("多行注释使用/*注释内容*/");
   /*
    多行注释
    养成书写注释的良好习惯
   */
</script>
```

##### 变量

变量是用于存储数据的存储器，JavaScript定义变量采用：

```javascript
var 变量名;
```

变量名可以任取，但是必须遵循以下规定：

1. 变量名必须使用字母、下划线或者美元符($)开始；
2. 可以使用任意多个英文字母、数字、下划线或者美元符($)组成；
3. 不能使用JavaScript关键词与保留字。

**变量要先声明，再赋值**

注：JavaScript区分大小写；变量先声明，再使用。

##### 判断语句`if···else`

在条件成立时执行`if`语句，不成立时执行`else`后代码。

语法：

```javascript
if(条件)
{ 条件成立时执行的代码 }
else
{ 条件不成立时执行的代码 }
```

##### 函数

函数是完成某个特定功能的一组语句，可以重复调用。

语法：

```javascript
function 函数名()
{
     函数代码;
}
```

说明：

1. function是定义函数的关键字；
2. 函数名是程序员为函数起的名字，方便以后调用（尽量有意义）；
3. 函数代码是特定功能的描述部分。

**函数调用**：

定义完函数后，可以直接使用**函数名调用函数**。

## 常用互动方法

##### 输出内容`document.write()`

使用`document.write()`可用于直接向html输出流写内容（直接在网页中输出内容）。

使用方法：

1. 将输出内容包裹在`""`中，可以直接输出其中的内容；

   ```javascript
         <script type="text/javascript">
           document.write("I love JavaScript！"); //内容用""括起来，""里的内容直接输出。
         </script>
   ```

2. 通过变量赋值，输出内容；

   ```javascript
   <script type="text/javascript">
     var mystr="hello world!";
     document.write(mystr);  //直接写变量名，输出变量存储的内容。
   </script>
   ```

3. 输出多项内容，内容之间用`+`连接；

   ```javascript
   <script type="text/javascript">
     var mystr="hello";
     document.write(mystr+"I love JavaScript"); //多项内容之间用+号连接
   </script>
   ```

4. 输出html标签，并起作用，标签使用`""`括起来。

   ```javascript
   <script type="text/javascript">
     var mystr="hello";
   document.write(mystr+"<br>");//输出hello后，输出一个换行符
     document.write("JavaScript");
   </script>
   ```

##### 警告（alert消息对话框）

在访问网站时突然弹出小窗口，标识者一段提示信息，不点“确定”便不能对网页做任何操作，这个窗口使用`alert()`实现。

语法：

```javascript
alert(字符串或变量);  
```

实例代码：

```javascript
<script type="text/javascript">
   var mynum = 30;
   alert("hello!");
   alert(mynum);
</script>
```

注：`alert`弹出消息对话框包含一个确定按钮。

输出的效果：

![alert](C:\Users\Tracy\Desktop\ScreenCut\alert.png)

单机确定按钮后：

![alert01](C:\Users\Tracy\Desktop\ScreenCut\alert01.png)

注意：

1. 在点击"确定"按钮之前，不能进行其他任何操作；
2. 消息对话框通常可以用于调试程序；
3. `alert()`输出内容可以是字符串或者变量，与`document.write()`相似。

##### 确认（confirm）消息对话框

`confirm`消息对话框通常用于允许用户做做选择的动作。弹出的对话框包括一个确定按钮和一个取消按钮。

语法：

```javascript
confirm(str);
```

参数说明：

```javascript
str：在消息对话框中要显示的文本
返回值: Boolean值
```

返回值：

```javascript
当用户点击"确定"按钮时，返回true
当用户点击"取消"按钮时，返回false
```

注：通过返回值可以判断用户点击的按钮。

实例代码：

```javascript
<script type="text/javascript">
    var mymessage=confirm("你喜欢JavaScript吗?");
    if(mymessage==true)
    {   document.write("很好,加油!");   }
    else
    {  document.write("JS功能强大，要学习噢!");  }
</script>
```

![confirm](C:\Users\Tracy\Desktop\ScreenCut\confirm.png)

注：消息框时排它的，用户在点击对话框按钮前不能进行任何其他操作。

##### 提问（prompt）消息对话框

`prompt`弹出消息对话框，通常用于询问一些需要交互性的信息。包括一个确定按钮、取消按钮与一个文本输入框。

语法：

```javascript
prompt(str1, str2)
```

参数说明：

```javascript
str1: 要显示在消息对话框中的文本，不可修改
str2：文本框中的内容，可以修改(默认显示在文本框中的内容)
```

返回值：

```javascript
1. 点击确定按钮，文本框中的内容将作为函数返回值
2. 点击取消按钮，将返回null
```

实例代码：

```javascript
var myname=prompt("请输入你的姓名:");
if(myname!=null)
  {   alert("你好"+myname); }
else
  {  alert("你好 my friend.");  }
```

![prompt](C:\Users\Tracy\Desktop\ScreenCut\prompt.png)

##### 打开新窗口

`open()`方法可以查找一个已经存在或者新建的浏览器窗口。

语法：

```javascript
window.open([URL], [窗口名称], [参数字符串])
```

参数说明：

```javascript
URL：可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档。
窗口名称：可选参数，被打开窗口的名称。
    1.该名称由字母、数字和下划线字符组成。
    2."_top"、"_blank"、"_selft"具有特殊意义的名称。
       _blank：在新窗口显示目标网页
       _self：在当前窗口显示目标网页
       _top：框架网页中在上部窗口中显示目标网页
    3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
    4.name 不能包含有空格。
参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。
```

|     参数     |     值     |       说明       |
| :--------: | :-------: | :------------: |
|    top     |  number   | 窗口顶部离开屏幕顶部的像素数 |
|    left    |  number   | 窗口左端离开屏幕左端的像素数 |
|   width    |  number   |     窗口的宽度      |
|   height   |  number   |     窗口的高度      |
|  menubar   | yes or no |     窗口有无菜单     |
|  toolbar   | yes or no |    窗口有无工具条     |
| scrollbars | yes or no |    窗口有无滚动条     |
|   status   | yes or no |    窗口有无状态栏     |

实例代码：打开http://www.imooc.com网站，大小为300px * 200px，无菜单，无工具栏，无状态栏，有滚动条窗口。

```javascript
<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
</script>
```

注意：运行结果考虑浏览器的兼容问题。

##### 关闭窗口

`close()`关闭窗口。

语法 ：

```javascript
window.close();   //关闭本窗口
```

或者：

```javascript
<窗口对象>.close();   //关闭指定的窗口
```

实例代码：关闭新建窗口

```javascript
<script type="text/javascript">
   var mywin=window.open('http://www.imooc.com'); //将新打的窗口对象，存储在变量mywin中
   mywin.close();
</script>
```

注意：以上代码再打开窗口的同时关闭该窗口，看不到被打开的窗口。

## DOM操作

##### 认识DOM

文档对象模型DOM(Document Object Model)定义访问和处理html文档的标准方法。DOM将html文档呈现为带有元素、属性和文本结构的树结构（节点树）。

```html
<!DOCTYPE HTML>
<html>
  <head>
    <meta http-equiv="COntent-Type" content="text/html"; charset=utf-8 />
    <title>DOM操作</title>
  </head>
  <body>
    <h2>
      <a href="http://www.imooc.com/">JavaScript DOM</a>
    </h2>
    <p>
      对html元素进行操作，可以添加、移除或改变css样式等。
    </p>
    <ul>
      <li>JavaScript</li>
      <li>DOM</li>
      <li>CSS</li>
    </ul>
  </body>
</html>
```

将上述html代码分解为DOM节点层次图：

![dom](C:\Users\Tracy\Desktop\ScreenCut\dom.png)

注：html文档由节点构成，以下是三种常见的DOM节点：

1. 元素节点：上图中`<html>、<body>、<p>`等都输元素节点（标签）；
2. 文本节点：向用户展示的内容，如`<li>···<li>`中的JavaScript、DOM、CSS等文本；
3. 属性节点：元素的属性，如`<a>`标签中的链接属性`href="http://www.imooc.com/"`。

```html
<a href="http://www.imooc.com">JavaScript DOM</a>
```

![dom1](C:\Users\Tracy\Desktop\ScreenCut\dom1.png)



##### 通过ID获取元素

学习html/css时，网页由标签将信息组织起来，标签的id属性值是唯一的，类似每个人的身份证。通过id值找到标签，再对其进行操作。

语法：

```javascript
document.getElementById("id");
```

实例代码：

```html
<!DOCTYPE HTML>
<html>
  <head>
    <meta http-equiv="COntent-Type" content="text/html"; charset=utf-8 />
    <title>获取元素</title>
    <script type="text/javascript">
    	var myId=document.getElementById("con");//获取元素并保存在变量myId中
        document.write(myId);  //输出变量myId
    </script>
  </head>
  <body>
	<h3>Hello</h3>
    <p id="con">
      I love 
    </p>
  </body>
</html>
```

注：结果为null或者[object HTMLParagraphElement]（html段落元素对象）。获取的元素是一个对象，同过元素的属性或者方法操作元素。

##### innerHTML属性

`innerHTML`属性用于获取或替换html元素的内容。

语法：

```javascript
Object.innerHTML
```

注意：

1. Object是获取的元素对象，例如通过`document.getElementById()`获取的元素；

2. 注意书写，`innerHTML`区分大小写。

3. 实例代码：

   ```html
   <!DOCTYPE HTML>
   <html>
   	<head>
         <title>innerHTML</title>
    	</head>
   	<body>
       	<p id="con">Hello world!</p>
         	<script>
         		var mycon=document.getElementById("con");
             	document.write("原来的内容："+ mycon.innerHTML+ <br >);
               mycon.innerHTML="New text!";
               document.write("现在的内容："+ mycon.innerHTML);
         </script>
   	</body>
   </html>
   ```

   ![inner](C:\Users\Tracy\Desktop\ScreenCut\inner.png)


##### 改变html样式

html DOM允许JavaScript改变html元素的样式。

语法：

```javascript
Object.style.property=new style;
```

注意：Object是获取的元素对象。

基本属性表（property）：

|       属性        |      概述      |
| :-------------: | :----------: |
| backgroundColor |  设置元素的背景颜色   |
|     height      |   设置元素的高度    |
|      width      |   设置元素的宽度    |
|      color      |   设置文本的颜色    |
|      font       | 在一行设置所有的字体属性 |
|   fontFamily    |  设置元素的字体系列   |
|    fontSize     |  设置元素的字体大小   |

注：以上只是一小部分css样式属性，其他样式也可以通过该方法设置和修改。

实例代码：

```javascript
p id="pcon">Hello World!</p>
<script>
   var mychar = document.getElementById("pcon");
   mychar.style.color="red";
   mychar.style.fontSize="20";
   mychar.style.backgroundColor ="blue";
</script>
```

##### 隐藏和显示（display属性）

网页中经常看到显示和隐藏的效果，可以通过display属性来设置。

语法：

```javascript
Object.style.display = value
```

value的取值：

| value |   description    |
| :---: | :--------------: |
| none  |  此元素不会被显示（即隐藏）   |
| block | 此元素将显示为块级元素（即显示） |

##### 控制类名（className属性）

`className`属性设置或返回元素的class属性。

语法：

```javascript
Object.className = classname
```

作用：

1. 获取元素的class属性；
2. 为网页内某个元素指定一个css样式来改变该元素的外观。








