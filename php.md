# php

### 1.安装phpstudy

看自己ip地址

ipconfig 内网下的ipv4地址

![image-20200722152500090](C:\Users\86137\Desktop\新建文件夹 (2)\image-20200722152500090.png)

> php是一种后台编程语言；使用php可以开发动态网站和后台接口（所谓接口就是url地址，用于给前端提供数据）。
>
> 
### 2.基本语法

php中的html标签之间要用''单引号弄住

连接数据时左右要有. --. 两个.

```php
<?php

header('content-type:text/html;charset=utf-8'); //编码格式

$name='吴京';
echo $name;
echo '<br>';

for($i=0;$i<10;$i++)
{
    echo 'hhhh';
}
while($num<999)
{
    echo 'hhh';
    $num++;
}

$foodArr=array('11','1132');

echo $foodArr[1];

//输出整个数组
print_r($foodArr);

//遍历整个数组

for($i=0;$i<count($foodArr);$i++)
{
//
}
$person=array('name'=>'吴京','film'=>'战狼');

print_r($person);

//key 是循环的健，就是name film
//value是吴京等
foreach($person as $key => $value)
{
    echo $key.'-------'.$value.'<br>';
}

$starArr=array(
    array('name'=>'甘草','film'=>'2'),
    array('name'=>'甘草','film'=>'2'),
    array('name'=>'甘草','film'=>'2'),

);
for($i=0;$i<count($starArr);$i++)
{
    echo '明星'.$starArr[$i]['name'].'<br>';
}

include '02.php';
echo '<ul>';
for($i=0;$i<2;$i++)
{
    echo '<li>';
    echo '<span>'.$foodArr[$i]['name'].'</span>';
    echo '</li>';
}
echo '</ul>';
?>
```

### 3.引入其他php

```php
include '02.php';
echo '<ul>';
for($i=0;$i<2;$i++)
{
    echo '<li>';
    echo '<span>'.$foodArr[$i]['name'].'</span>';
    echo '</li>';
}
echo '</ul>';
?>
```

### 4.form后台接收数据

![image-20200723085058443](C:\Users\86137\Desktop\新建文件夹 (2)\image-20200723085058443.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php
    header('content-type:text/html;charset=utf-8'); //编码格式
    $heroName=$_GET['hero']; //中括号要记住了
    include './lol.php';
    $hero=$heroArr[$heroName];

    echo '<h2>'.$hero['champion'].'</h2>';

    ?>
</body>
</html>
```

### 5.php的拆分

```php
<?php for($i=0;$i<12;$i++) { ?>

    <h1>hhhhhh  </h1>
    <h1><?php echo $hero ?></h1>
<?php } ?>
```

不拆分的话，用.连接 可能看起来麻烦，这样能方便一些

### 6.提交文件

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="./file.php" method="POST" enctype="multipart/form-data"> /*看好这里的格式*/
    <input type="file" name="icon">
    <br>
    <input type="submit">
    
    
    </form>
</body>
</html>
```

### 7.ajax的get请求

html：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>哈哈哈哈哈哈</h2>
    <input type="text" placeholder="请输入用户名">
</body>
</html>
<script>
    document.querySelector('input').onblur=function()
    {
        //1.创建异步对象
        var xhr=new XMLHttpRequest();
        //2.设置请求行
        xhr.open('get','checkName.php?name='+this.value);
        //3.设置请求头
        //5.注册回调函数
        xhr.onload=function()
        {
            document.querySelector('h2').innerHTML=xhr.responseText;
        }

        //4.请求主体发送
        xhr.send(null);
    }
</script>
```

php

```php
<?php

$name=$_GET['name'];
$nameArr=array('jack','rose');

$result= in_array($name,$nameArr);

if($result==true)
{
    echo '很遗憾，有人用了';
}
else{
    echo '恭喜你，你是第一个';
}

?>
```

### 8.ajax的post请求

```php
document.querySelector('input').onblur=function()
    {
        //1.创建异步对象
        var xhr=new XMLHttpRequest();
        //2.设置请求行
        xhr.open('post','checkName.php);
        //3.设置请求头 //很重要
        xhr.setRequestHeader("Content-type","application/x-www-form-urlencoded");
        //5.注册回调函数
        xhr.onload=function()
        {
            document.querySelector('h2').innerHTML=xhr.responseText;
        }

        //4.请求主体发送
        xhr.send('name=jack&name2=rose');
    }
```

### 9.jq和ajax的机器人使用

```html
<script>

$(function(){
    $(".sendButton").click(function(){
        var $cloneSelf=$("self").first().clone();
        $(".message").append($cloneSelf);
        $cloneSelf.show();
        $cloneSelf.find('p').html($('.inputBox').val());
        
        var xhr =new XMMLHttpRequest();
        xhr.open('post','chat.php');
        
        xhr.onload=function(){
            var ￥cloneRobot=$('.robot').first().clone();
            $cloneRobot.appendTo('.message');
            $cloneRobot.find('p').html(xhr.responseText);
            
            xhr.send(null);
        }
    })
})

</script>
```

```php
<?php
    
    $messageList=array(
	'nihao',
    'hhhhh'

);

$randomKey =array_rand($messageList,1);
echo $messageList[$randomKey];
?>
```

### 10.新浪云 互联网环境

![image-20200724100212360](C:\Users\86137\Desktop\新建文件夹 (2)\image-20200724100212360.png)

### 11.切换姓名图片

```html
<script>
$('input').click(function(){
    var xhr=new XMLHttpRequest();
    xhr.open('get','get.php?name='+$(this).val());
    xhr.onreadystatechange=function(){
        if(xhr.readyState==4&&xhr.status ==200)
            {
			$('img').attr('src',xhr.responseText);
            }
    }
    xhr.send(null);
})
</script>
```

```php
<?php
$strname=$_GET['name'];
$name=array(
'wujing'=>array('icon'=>'img/11.png'),
    

);
$someone=$name[$strname];
echo $someone['icon'];
?>
```

### 12.ajax中split用法

```html
var result=xhr.responseText.split('|||');
$('img').attr('src',result[0]);
$('p').html(result[1]);
```

```
echo $someone['icon'];
echo '||||';
echo $someone['info'];
```

### 13.服务器返回xml文件

```php
<?php

header('content-type':text/xml;charset=utf-8');
$xmlString=file_get_contents('data/data.xml');
echo $xmlSting;
?>
```

```
xhr.responseXML;
var name=xhr.responseXML.querySelector('name').innerHTML;

```

```
doucument.querySelector('h3').innerHTML=name+'---';
```

### 14.xml和dom添加的结合

```html
<script>
    
    var allHero =xhr.responseXML.querySelectorALL('hero');
    
var ulDom=doucument.crerateElement('ul');
    doucument.body.appendChild(ulDom);
    for(var i=0;i<allHero.length;i++)
        {
            var currentHero=allHero[i];
            var icon=currentHero.querySelector('icon').innerHTML;
           var liDom=doucument.createElement('li');
            liDom.innerHTML='<img src="'+icon+'">'
            ulDom.appenChild(liDom);
        }

</script>
```

### 15.get的url接口

```
doucument.querySelector('input[type=button]').onclick=function(){
var xhr=new XMLHttpRequest();
xhr.open('get','http://-----?city='+doucument.querySelector('input[type=text]').value);
}
```

### 16.xml举例

```xml
<?xml version="1.0" encoding="utf-8"?>
<note>
<to>George</to>
<from>John</from>
<heading>Reminder</heading>
<body>Don't forget the meeting!</body>
</note>
```

### 17.json数据

```html
<script>
    var JSONObject ='{"name":"刘亦菲"，"skill":"6666"}';
    console.log(JSONObject);
   
    var str = '{"name":"LeonWu","age":"18"}'

    var str2 =JSON.parse(str);
    console.log(str2);


    var JSONObjArr='{"name":"彭彭","skill":"约跑","run":["11","22"]}'
    console.log(JSONObjArr);
    var result=JSON.parse(JSONObjArr);
    console.log(result);
</script>
```

### 18.ajax解析json

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>哈哈哈哈哈哈</h2>
    <input type="button" value="返回json">
</body>
</html>
<script>
    document.querySelector('input').onclick=function()
    {
        //1.创建异步对象
        var xhr=new XMLHttpRequest();
        //2.设置请求行
        xhr.open('post','backJSON.php');
        //3.设置请求头
        //5.注册回调函数
        xhr.onload=function()
        {
            var arr=JSON.parse(xhr.responseText);

            for(var i=0;i<arr.length;i++)
            {
                var currentObj=arr[i];
                console.log(currentObj.name);
            }
        }

        //4.请求主体发送
        xhr.send(null);
    }
</script>
```

```php
<?php
$jsonString=file_get_contents('star.json');
echo $jsonString;

?>
```

```json
[
    {
        "name":"吴京",
        "skill":"6666"
    },
    {
        "name":"成龙",
        "skill":"6696"
    },
    {
        "name":"杨紫",
        "skill":"60006"
    }

]
```

### 19.想修改类中标签的数据

这里用的是jq，dataobj是解析的json数据，里面有一个data数组

```
$('.jumbotron').find('span').first().html(dataObj.data.champion);
$('.jumbotoron').find('img').attr('src',dataObj.data.champion-icon);
```

### 20.点击图片触发事件

```
$('.row').on('click','a',function(){

})
```



## php基础语法

- 变量
- 字符串拼接
- 单引号与双引号
- 内容输出
- 数据类型
- 运算符
- 分支循环语句
- 函数
- 预定义变量（表单处理）
## 变量
> 变量以$开头 字母/数字/下划线 不能以数字开头，大小写敏感。
## 内容输出
- echo：输出简单数据类型，如字符串、数值
- print_r()：输出复杂数据类型，如数组
- var_dump()：输出详细信息，如对象、数组
## 字符串拼接
- js中字符串拼接用+；php中字符串拼接用.
## 单引号与双引号
- 单引号中的变量会当作普通字符串处理
- 双引号中的变量会解析为变量值
## 运算符
- 与JavaScript基本类似
## 数据类型
- 字符串
- 整型
- 浮点型
- 布尔型
- 数组
- 对象
- NULL
## 预定义变量（表单处理）
- $_GET

- ```
  $_GET变量
  通过 URL 参数传递给当前脚本的变量的数组，不需要通过global引用。GET 是通过 urldecode() 传递的

  $_GET 变量是一个数组，内容是由 HTTP GET 方法发送的变量名称和值。
  从带有 GET 方法的表单发送的信息，对任何人都是可见的（会显示在浏览器的地址栏），并且对发送的信息量也有限制（最多 100 个字符），所以参数的长度不是无限的，但是基本都能满足我们的要求了。
  
  $_GET 变量用于收集来自 method='get'的表单中的值，直观的的就是浏览器中可以看到的参数，比如我在百度搜索“wordpress”的时候，我请求的url就是(http://www.baidu.com/s?ie=utf-8&bs=wordpress&f=8&rsv_bp=1&wd=wordpress&inputT=0)，那么'?'后面的参数都是可以用$_GET获取，各个参数是以'&'作为分隔符的。
  
  $_POST变量
  当 HTTP POST 请求的 Content-Type 是 application/x-www-form-urlencoded 或 multipart/form-data 时，会将变量以关联数组形式传入当前脚本。
  
  $_POST 变量是一个数组，内容是由 HTTP POST 方法发送的变量名称和值。
  
  $_POST 变量用于收集来自 method=”post” 的表单中的值。
  从带有 POST 方法的表单发送的信息，对任何人都是不可见的（不会显示在浏览器的地址栏），并且对发送信息的量也没有限制
  
  作者：旅行者xy
  链接：https://www.jianshu.com/p/9b7f0d2995be
  来源：简书
  著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
  ```
  
- 

- 

- $_POST
## 分支循环
- if/switch

- while

- for

- foreach

- ```php
  从php5开始，可以$value 之前加上 & 来修改数组的元素。
  此方法将以引用赋值而不是拷贝一个值，减少了空间浪费，是个不错的方法。
  
  例子：
  
  <?php
  $arr = array(1, 2, 3, 4);
  foreach ($arr as &$value) {
      $value = $value * 2;
  }
  // $arr is now array(2, 4, 6, 8)
  ?>
  此方法仅在被遍历的数组可以被引用时才可用（例如是个变量）。
  
  例子：
  
  <?php
  foreach (array(1, 2, 3, 4) as &$value) {
      $value = $value * 2;
  }
  ?>
  ```

- ```php
   header('Content-Type:text/html; charset=utf-8');
  ```

- 
## 函数
### 自定义函数
- 语法规则（函数名不区分大小写）
### 系统函数
- gettype()
- json_encode() //将数组或者对象转换成字符串形式

```php
$arr=array("username"=>"zhangsan",~)
echo json_encode($arr);
```

