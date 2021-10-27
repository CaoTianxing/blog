---
title: Javascript中最常用的61个经典技巧 
date: 2021-10-27 20:38:53 
tags: JavaScript 
categories:
- 前端
---

### 彻底屏蔽鼠标右键

```html
oncontextmenu="window.event.returnValue=false"
```

### 取消选取、防止复制

```html

<body onselectstart="return false">
```

### 不准粘贴

```html
onpaste="return false"
```

### 防止复制

```html
oncopy="return false;" oncut="return false;"
```

### IE地址栏前换成自己的图标

```html

<link rel="Shortcut Icon" href="favicon.ico">
```

### 可以在收藏夹中显示出你的图标

```html

<link rel="Bookmark" href="favicon.ico">
```

### 关闭输入法

```html
<input style="ime-mode:disabled">
```

### 永远都会带着框架

```html

<script language="JavaScript">
    //frames.htm为框架网页
    if (window == top) top.location.href = "frames.htm";
</script>

```

### 防止被人frame

```html

<script language="JavaScript">
    if (top.location != self.location) top.location = self.location;
</script>
```

### 网页将不能被另存为

```html

<noscript><*** src="/*.html>";</***></noscript>
```

### 查看网页源代码

```html
<input type=button value="/查看网页源代码
    onclick=" window.location="view-source:" + "http://www.pconline.com.cn"">
```

### 删除时确认

```html
<a href="" javascript :if(confirm("确实要删除吗?"))location="boos.asp?&areyou=删除&page=1"">删除</a>
```

### 取得控件的绝对位置

```html

<script language="Javascript">
    function getIE(e) {
        var t = e.offsetTop;
        var l = e.offsetLeft;
        while (e = e.offsetParent) {
            t += e.offsetTop;
            l += e.offsetLeft;
        }
        alert("top=" + t + "/nleft=" + l)
    }
</script>
```

### 光标是停在文本框文字的最后

```html

<script language="javascript">
    function cc() {
        var e = event.srcElement;
        var r = e.createTextRange()
        r.moveStart("character", e.value.length)
        r.collapse(true)
        r.select()
    }

</script>
<input type=text name=text1 value="123" onfocus="cc()">
```

### 判断上一页的来源

```javascript
 document.referrer
```

### 最小化、最大化、关闭窗口

```html

<object id=hh1 classid="clsid:ADB880A6-D8FF-11CF-9377-00AA003B7A11">
    <param name="Command" value="Minimize">
</object>
<object id=hh2 classid="clsid:ADB880A6-D8FF-11CF-9377-00AA003B7A11">
    <param name="Command" value="Maximize">
</object>
<OBJECT id=hh3 classid="clsid:adb880a6-d8ff-11cf-9377-00aa003b7a11">
    <PARAM NAME="Command" value="/Close">
</OBJECT>
<input type=button value="/最小化 onclick=hh1.Click()>
<input type=button value="/blog/最大化 onclick=hh2.Click()>
<input type=button value=关闭 onclick=hh3.Click()>
本例适用于IE

```

### 屏蔽功能键Shift,Alt,Ctrl

```html

<script>
    function look() {
        if (event.shiftKey)
            alert("禁止按Shift键！"); //可以换成ALT　CTRL
    }

    document.onkeydown = look;
</script>

```

### 网页不会被缓存

```html

<meta HTTP-EQUIV="pragma" CONTENT="no-cache">
<meta HTTP-EQUIV="Cache-Control" CONTENT="no-cache, must-revalidate">
<meta HTTP-EQUIV="expires" CONTENT="Wed, 26 Feb 1997 08:21:57 GMT">
或者
<meta HTTP-EQUIV="expires" CONTENT="0">
```

### 怎样让表单没有凹凸感?

```html
<input type=text></input>
<style>
    input {
        border-left: none;
        border-right: none;
        border-top: none;
        border-bottom: 1px solid #000000
    }
</style>
```

### div,span & layer的区别?

```html

<div>(division)用来定义大段的页面元素,会产生转行
    <span>用来定义同一行内的元素,跟<div>的唯一区别是不产生转行
 <layer>是ns的标记,ie不支持,相当于<div>

```

### 让弹出窗口总是在最上面

```html

<body onblur="this.focus();">
```

### 不要滚动条?

```html
让竖条没有：
<body style="overflow:scroll;overflow-y:hidden"></body>
让横条没有：
<body style="overflow:scroll;overflow-x:hidden"></body>
两个都去掉?更简单了
<body scroll="no"></body>
```

### 怎样去掉图片链接点击后,图片周围的虚线?

```html
 <a href="#" onFocus="this.blur()"><img src="/logo.jpg" border=0></a>
```

### 电子邮件处理提交表单

```html

<form name="form1" method="post" action=mailto:****@***.com enctype="text/plain">
    <input type=submit>
</form>
```

### 在打开的子窗口刷新父窗口的代码里如何写?

```javascript
window.opener.location.reload()
```

### 如何设定打开页面的大小

```html

<body onload="top.resizeTo(300,200)">
```

### 在页面中如何加入不是满铺的背景图片,拉动页面时背景图不动

```css
body {
    background-image: url('logo.gif');
    background-repeat: no-repeat;
    background-position: center;
    background-attachment: fixed
}
```

### 检查一段字符串是否全由数字组成

```javascript
const checkNum = (str) => {
    str.match(/D/) == null
}
console.log(checkNum("1232142141"))
console.log(checkNum("123214214a1"))
```

### 获得一个窗口的大小

```javascript
document.body.clientWidth;
document.body.clientHeight
```

### 怎么判断是否是字符

```javascript
if (/[^/x00-/xff]/g.test(s)) {
    alert("含有汉字")
} else alert("全是字符")
```

### TEXTAREA自适应文字行数的多少

```html
<textarea rows=1 name=s1 cols=27 onpropertychange="this.style.posHeight=this.scrollHeight"></textarea>
```

### 日期减去天数等于第二个日期

```javascript
function cc(dd, dadd) {
    //可以加上错误处理
    var a = new Date(dd)
    a = a.valueOf()
    a = a - dadd * 24 * 60 * 60 * 1000
    a = new Date(a)
    alert(a.getFullYear() + "年" + (a.getMonth() + 1) + "月" + a.getDate() + "日")
}

cc("12/23/2002", 2)
```

### 选择了哪一个Radio

```javascript
function checkme(nodeName) {
    const nodeList = document.querySelectorAll('.nodeName') || []
    nodeList.forEach((v, i, a) => {
        if (v.checked) {
            console.log('选中索引值为', i)
        }
    })
}
```

### 脚本永不出错

```javascript
function killErrors() {
    return true;
}

window.onerror = killErrors;
```

### ENTER键可以让光标移到下一个输入框

```html
<input onkeydown="if(event.keyCode==13)event.keyCode=9">
```

### 检测某个网站的链接速度：

```javascript
document.write('<div id="msg">正在测试网络延迟,请稍后...</div>');
document.write('<a href="#">电信网路</a>    <span class="classtime" xl-name="电信网路"></span><br>');
document.write('<a href="#">联通网路</a>    <span class="classtime" xl-name="联通网路"></span>');
var jump = 1, t = {}, autourl = new Array(), autoname = [];
autourl[1] = "http://image.baidu.com/"; //这个是电信服务器站点
autourl[2] = "https://www.baidu.com/"; //这个是联通服务器站点
autoname[1] = "电信网路";
autoname[2] = "联通网路";
(function () {
    for (var i = 1; i < autourl.length; i++) {
        var img = new Image;
        //img.onerror= auto(autourl[i]);
        img.onerror = (function (j) {
            return function () {
                t[autourl[j]] = (new Date()) - t[autourl[j]];  //记入时间差
                console.log(autourl[j] + "    ：" + t[autourl[j]] + "ms"); //console.log(t[url] + "ms");
                document.querySelector('[xl-name="' + autoname[j] + '"]').innerHTML = t[autourl[j]] + ' ms';
                console.log(jump);
                if (jump) {
                    jump = 0;
                    document.getElementById("msg").innerText = '3秒后进入【' + autoname[j] + '】';
                    //setTimeout(function(){top.location=url;},3000); //setTimeout("top.location='" + url + "';",3000);   //3s 即3000ms
                    setTimeout(function () {
                        window.location.replace(autourl[j]);
                    }, 3000);
                }
            }
        })(i);
        //闭包传值
        img.src = autourl[i] + Math.random();
        t[autourl[i]] = (+new Date());//记录开始载入时间
    }
})();
```

### 各种样式的光标

```html
auto ：标准光标
default ：标准箭头
hand ：手形光标
wait ：等待光标
text ：I形光标
vertical-text ：水平I形光标
no-drop ：不可拖动光标
not-allowed ：无效光标
help ：?帮助光标
all-scroll ：三角方向标
move ：移动标
crosshair ：十字标
e-resize
n-resize
nw-resize
w-resize
s-resize
se-resize
sw-resize
```

### 页面进入和退出的特效

```html
进入页面
<meta http-equiv="Page-Enter" content="revealTrans(duration=x, transition=y)">
推出页面
<meta http-equiv="Page-Exit" content="revealTrans(duration=x, transition=y)">
这个是页面被载入和调出时的一些特效。duration表示特效的持续时间,以秒为单位。transition表示使用哪种特效,取值为1-23:
0 矩形缩小
1 矩形扩大
2 圆形缩小
3 圆形扩大
4 下到上刷新
5 上到下刷新
6 左到右刷新
7 右到左刷新
8 竖百叶窗
9 横百叶窗
10 错位横百叶窗
11 错位竖百叶窗
12 点扩散
13 左右到中间刷新
14 中间到左右刷新
15 中间到上下
16 上下到中间
17 右下到左上
18 右上到左下
19 左上到右下
20 左下到右上
21 横条
22 竖条
23 以上22种随机选择一种
```

### 在规定时间内跳转

```html

<meta http-equiv=V="REFRESH" content="5;URL=https://www.baidu.com">
```

### 网页是否被检索

```html

<meta name="ROBOTS" content="属性值">
其中属性值有以下一些：
属性值为"all": 文件将被检索,且页上链接可被查询;
属性值为"none": 文件不被检索,而且不查询页上的链接;
属性值为"index": 文件将被检索;
属性值为"follow": 查询页上的链接;
属性值为"noindex": 文件不检索,但可被查询链接;
属性值为"nofollow": 文件不被检索,但可查询页上的链接。
```

### email地址的分割

```html
把如下代码加入
<body>区域中
<a href="mailto:webmaster@sina.com">webmaster@sina.com</a>
```

### 流动边框效果的表格

```javascript
l = Array(6, 7, 8, 9, 'a', 'b', 'b', 'c', 'd', 'e', 'f')
Nx = 5;
Ny = 35
t = "<table border=0 cellspacing=0 cellpadding=0 height=" + ((Nx + 2) * 16) + "><tr>"
for (x = Nx; x < Nx + Ny; x++)
    t += "<td width=16 id=a_mo" + x + ">　</td>"
t += "</tr><tr><td width=10 id=a_mo" + (Nx - 1) + ">　</td><td colspan=" + (Ny - 2) + " rowspan=" + (Nx) + ">　</td><td width=16 id=a_mo" + (Nx + Ny) + "></td></tr>"
for (x = 2; x <= Nx; x++)
    t += "<tr><td width=16 id=a_mo" + (Nx - x) + ">　</td><td width=16 id=a_mo" + (Ny + Nx + x - 1) + ">　</td></tr>"
t += "<tr>"
for (x = Ny; x > 0; x--)
    t += "<td width=16 id=a_mo" + (x + Nx * 2 + Ny - 1) + ">　</td>"
    (t + "</tr></table>")
var N = Nx * 2 + Ny * 2

function f1(y) {
    for (i = 0; i < N; i++) {
        c = (i + y) % 20;
        if (c > 10) c = 20 - c
        document.all["a_mo" + (i)].bgColor = `#0000+${l[c]}${l[c]}`
        y++
        setTimeout('f1(' + y + ')', '1')
    }
}

f1(1)
```

### JavaScript主页弹出窗口技巧

```html
 窗口中间弹出
<script>
    window.open("http://www.cctv.com", "", "width=400,height=240,top=" + (screen.availHeight - 240) / 2 + ",left=" + (screen.availWidth - 400) / 2);
</script>
============
<html>
<head>
    <script language="LiveScript">
            function WinOpen() {
            msg=open("","DisplayWindow","toolbar=no,directories=no,menubar=no");
            msg.***("<HEAD><TITLE>哈 罗！</TITLE></HEAD>");
            msg.***("<CENTER><H1>酷 毙 了！</H1><h2>这 是<B>JavaScript</B>所 开 的 视 窗！</h2></CENTER>");
        }
        
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    </script>
</head>
<body>
<form>
    <input type="button" name="Button1" value="Push me" onclick="WinOpen()">
</form>
</body>
</html>
==============
一、在下面的代码中,你只要单击打开一个窗口,即可链接到天下网。而当你想关闭时,只要单击一下即可关闭刚才打开的窗口。
代码如下：
<SCRIPT language="JavaScript">

    function openclk() {
        another = open('1000){this.resized=true;this.style.width=1000;}" align=absMiddle border=0>www.netskycn.com', 'NewWindow');
    }

    function closeclk() {
        another.close();
    }

</SCRIPT>
<FORM>
    <INPUT TYPE="BUTTON" NAME="open" value="/打开一个窗口" onClick="openclk()">
    <BR>
    <INPUT TYPE="BUTTON" NAME="close" value="/blog/关闭这个窗口" onClick="closeclk()">
</FORM>
二、上面的代码也太静了,为何不来点动感呢?如果能给页面来个降落效果那该多好啊！
代码如下：
<script>
    function drop(n) {
        if (self.moveBy) {
            self.moveBy(0, -900);
            for (i = n; i > 0; i--) {
                self.moveBy(0, 3);
            }
            for (j = 8; j > 0; j--) {
                self.moveBy(0, j);
                self.moveBy(j, 0);
                self.moveBy(0, -j);
                self.moveBy(-j, 0);
            }
        }
    }
</script>
<body onLoad="drop(300)">
三、讨厌很多网站总是按照默认窗口打开,如果你能随心所欲控制打开的窗口那该多好。
代码如下：
<SCRIPT LANGUAGE="JavaScript">
    function popupPage(l, t, w, h) {
        var windowprops = "location=no,scrollbars=no,menubars=no,toolbars=no,resizable=yes" +
                ",left=" + l + ",top=" + t + ",width=" + w + ",height=" + h;
        var URL = "http://www.netskycn.com";
        popup = window.open(URL, "MenuPopup", windowprops);
    }

    // End -->
</script>
<table>
    <tr>
        <td>
            <form name=popupform>
    <pre>
    打开页面的参数<br>
    离开左边的距离： <input type=text name=left size=2 maxlength=4> pixels
    离开右边的距离： <input type=text name=top size=2 maxlength=4> pixels
    窗口的宽度： <input type=text name=width size=2 maxlength=4> pixels
    窗口的高度： <input type=text name=height size=2 maxlength=4> pixels
    </pre>
                <center>
                    <input type=button value="打开这个窗口！" onClick="popupPage(this.form.left.value, this.form.top.value, this.form.width.value,
    this.form.height.value)">
                </center>
            </form>
        </td>
    </tr>
</table>
你只要在相对应的对话框中输入一个数值即可,将要打开的页面的窗口控制得很好。
```

### 页面的打开移动

```javascript
  for (t = 2; t > 0; t--) {
    for (x = 20; x > 0; x--) {
        for (y = 10; y > 0; y--) {
            parent.moveBy(0, -x);
        }
    }
    for (x = 20; x > 0; x--) {
        for (y = 10; y > 0; y--) {
            parent.moveBy(0, x);
        }
    }
    for (x = 20; x > 0; x--) {
        for (y = 10; y > 0; y--) {
            parent.moveBy(x, 0);
        }
    }
    for (x = 20; x > 0; x--) {
        for (y = 10; y > 0; y--) {
            parent.moveBy(-x, 0);
        }
    }
}
```

### 显示个人客户端机器的日期和时间

```javascript
today = new Date()

("现 在 时 间 是： ", today.getHours(), ":", today.getMinutes())
("<br>今 天 日 期 为： ", today.getMonth() + 1, "/", today.getDate(), "/", today.getYear());
```

### 自动的为你每次产生最後修改的日期了

```javascript
document.lastModified
```

### 不能为空和邮件地址的约束：

```html

<html>
<head>
    <script language="JavaScript">

        function test1(form) {
            if (form.text1.value == "")
                alert("您 没 写 上 任 何 东 西, 请 再 输 入 一 次 !")
            else {
                alert("嗨 " + form.text1.value + "! 您 已 输 入 完 成 !");
            }
        }

        function test2(form) {
            if (form.text2.value == "" ||
                    form.text2.value.indexOf('@', 0) == -1)
                alert("这 不 是 正 确 的 e-mail address! 请 再 输 入 一 次 !");
            else alert("您 已 输 入 完 成 !");
        }

        // -->
    </script>
</head>
<body>
<form name="first">
    Enter your name:<br>
    <input type="text" name="text1">
    <input type="button" name="button1" value="输 入 测 试" onClick="test1(this.form)">
    <P>
        Enter your e-mail address:<br>
        <input type="text" name="text2">
        <input type="button" name="button2" value="输 入 测 试" onClick="test2(this.form)">
</body>
```

### 跑马灯

```html

<html>
<head>
    <script language="JavaScript">

        var scrtxt = "怎麽样 ! 很酷吧 ! 您也可以试试。" + "Here goes your message the visitors to yourpage will " + "look at for hours in pure fascination…";

        var lentxt = scrtxt.length;
        var width = 100;
        var pos = 1 - width;

        function scroll() {
            pos++;
            var scroller = "";
            if (pos == lentxt) {
                pos = 1 - width;
            }
            if (pos < 0) {
                for (var i = 1; i <= Math.abs(pos); i++) {
                    scroller = scroller + " ";
                }
                scroller = scroller + scrtxt.substring(0, width - i + 1);
            } else {
                scroller = scroller + scrtxt.substring(pos, width + pos);
            }
            window.status = scroller;
            setTimeout("scroll()", 150);
        }

    </script>
</head>
<body onLoad="scroll();return true;">
这里可显示您的网页 !
</body>
</html>
```

### 在网页中用按钮来控制前页,后页和主页的显示。

```html

<form NAME="buttonbar">
    <input TYPE="button" value="Back" onClick="history.back()">
    <input TYPE="button" value="JS- Home" onClick="location='script.html'">
    <input TYPE="button" value="Next" onCLick="history.forward()">
</form>
```

### 查看某网址的源代码

```html
 把如下代码加入
<body>区域中
<script>
    function add() {
        var ress = document.forms[0].luxiaoqing.value
        window.location = "view-source:" + ress;
    }
</script>

// 输入要查看源代码的URL地址：
<form><input type="text" name="luxiaoqing" size=40 value="http://"></form>
<form><br><input type="button" value="查看源代码" onClick=add()></form>
```

### title显示日期

```html
把如下代码加入
<body>区域中：
<script language="JavaScript1.2">

    var isnMonth = new
    Array("1月", "2月", "3月", "4月", "5月", "6月", "7月", "8月", "9月", "10月", "11月", "12月");
    var isnDay = new
    Array("星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六", "星期日");
    today = new Date();
    Year = today.getYear();
    Date = today.getDate();
    if (document.all)
        document.title = "今天是： " + Year + "年" + isnMonth[today.getMonth()] + Date + "日" + isnDay[today.getDay()]
</script>
```

### 显示所有链接

```javascript

function extractlinks() {
    var links = document.all.tags("A")
    var total = links.length
    var win2 = window.open("", "", "menubar,scrollbars,toolbar")
    win2. * * * ("<font size='2'>一共有" + total + "个连接</font><br>")
    for (i = 0; i < total; i++) {
        win2. * * * ("<font size='2'>" + links[i].outerHTML + "</font><br>")
    }
}

< input type="button" onClick="extractlinks()" value="显示所有的连接">
```

### 回车键换行

```html
把如下代码加入
<body>区域中
<script type="text/javascript">
    function handleEnter(field, event) {
        var keyCode = event.keyCode ? event.keyCode : event.which ?
                event.which : event.charCode;
        if (keyCode == 13) {
            var i;
            for (i = 0; i < field.form.elements.length; i++)
                if (field == field.form.elements[i])
                    break;
            i = (i + 1) % field.form.elements.length;
            field.form.elements[i].focus();
            return false;
        } else
            return true;
    }
</script>
<form>
    <input type="text" onkeypress="return handleEnter(this, event)"><br>
    <input type="text" onkeypress="return handleEnter(this, event)"><br>
    <textarea>回车换行

```

### 确认后提交

```html

<script LANGUAGE="JavaScript">
    function msg() {
        if (confirm("你确认要提交嘛！"))
            document.lnman.submit()
    }
</script>
<form name="lnman" method="post" action="">
    <p>
        <input type="text" name="textfield" value="确认后提交">
    </p>
    <p>
        <input type="button" name="Submit" value="提交" onclick="msg();">
    </p>
</form>
```

### 改变表格的内容

```html

<script ***script>
    var arr = new Array()
    arr[0] = "一一一一一";
    arr[1] = "二二二二二";
    arr[2] = "三三三三三";
</script>
<select onchange="zz.cells[this.selectedIndex].innerHTML=arr[this.selectedIndex]">
    <option value=a>改变第一格</option>
    <option value=a>改变第二格</option>
    <option value=a>改变第三格</option>
</select>
<table id=zz border=1>
    <tr height=20>
        <td width=150>第一格</td>
        <td width=150>第二格</td>
        <td width=150>第三格</td>
    </tr>
</table>
```

### 获取当前浏览器地址URL:

```javascript
 var myURL = document.URL;
window.alert(myURL);
```

### 定时执行函数

```javascript
  function hello() {
    window.alert("Hello");
    window.setTimeout("hello()", 5000);
}

setTimeout(hello, 5000)
```

### 取消定时执行

```html
clearTimeout(myTimeout)
```

### 读取URL参数

```javascript
 var urlParts = document.URL.split("?");
var parameterParts = urlParts[1].split("&");
for (i = 0; i < parameterParts.length; i++) {
    var pairParts = parameterParts[i].split("=");
    var pairName = pairParts[0];
    var pairValue = pairParts[1];
    document.write(pairName + " ：" + pairValue);
}
```

### 读取图像属性

```html
<img src="/image1.jpg" name="myImage">
<a href="# " onClick="window.alert(document.myImage.width)">Width</a>
```

### 创建幻灯片

```html

<script language="JavaScript">
    var imageList = new Array;
    imageList[0] = new Image;
    imageList[0].src = "image1.jpg";
    imageList[1] = new Image;
    imageList[1].src = "image2.jpg";
    imageList[2] = new Image;
    imageList[2].src = "image3.jpg";
    imageList[3] = new Image;
    imageList[3].src = "image4.jpg";

    function slideShow(imageNumber) {
        document.slideShow.src = imageList[imageNumber].src;
        imageNumber += 1;
        if (imageNumber < imageList.length) {
            window.setTimeout("slideShow(" + imageNumber + ")", 3000);
        }
    }
</script>
</head>
<body onLoad="slideShow(0)">
<img src="/" image1.jpg"" width=100 name="slideShow">

```