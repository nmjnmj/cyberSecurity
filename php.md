PHP
php.net
一门编程语言
运行在服务器端的
专门用于开发网站的
解释型语言
PHP 运行需要运行环境，windows phpstudy
linux 单独安装
脚本后缀名.php
与HTML语言进行混编，脚本后缀名依然是PHP
# 概述
PHP的语法借鉴吸收了C语言、Java和Perl等流行计算机语言的特点，易于一般程序员学习
PHP的主要目标是允许网络开发人员快速编写动态页面
简单点说PHP主要被用于开发各种类型的网站程序
细化点说PHP可以用于收集表单数据，生成动态网页，字符串处理，动态输出图像，处理服务器端文件，与数据库交互，会话跟踪，处理XML文件，支持大量的网络协议，服务器端的其他相关操作
PHP是脚本语言不需要事先编译，在服务器上运行
PHP可以运行在Windows,linux等操作系统上

web工作原理概述
1. 浏览器
2. 输入url地址
3. 显示网站内容

PHP运行环境安装
Apache+PHP+MySQL是PHP比较流行的生存环境
LAMP

编辑器安装
zendstudio
notepad++

PHP 基本语法
  PHP 语言标记
    开始标记 <?php
    结束标记 ?>
1. <?php ?>之间就表示进入了PHP模式，在可以和结束标记之外的内容都会被PHP解析器忽略
2. 可以直接嵌入到html代码中，并且可以嵌入到html代码中的任何地方
3. 在一个html文档中可以嵌入任意多个PHP标记
4. 文件末尾的PHP代码段结束标记可以不要，在一些情况下省略掉更好

指令分隔符[;]
1. PHP用分号表示一句话的结束
2. 结束标记?>就隐含一个分号，所以PHP代码最后一行可以不用加分号

注释
/*这是一个多行注释，可以有多行文字*/
//这是单行注释

注意 PHP代码中注释不会显示在浏览器的源代码中
PHP 运行环境是服务器，浏览器端看到的是PHP引擎运行PHP代码后的执行结果

## 遇到空白的处理
空白符包括
空格 tab键 换行
这些在PHP中都是无关紧要的（注意都是英文输入法下的），可以将一个语句展开成任意行，或者紧缩在一行，空格与空行的合理运用可以增强代码的清晰性与可读性，如果运用不合理反而会对阅读产生负担

## 变量
现实生活中，在家里用柜子来存放衣服 包 书籍等等其他的东西
变量是用于临时存储值得容器
变量在任何编程语言中都是核心地位
PHP脚本语言是一种弱类型语言，和其他语言不同的是变量或者常量得数据类型由程序得上下文决定

变量的声明：
  PHP得特性之一就是它不要求在使用之前声明变量，当第一次给一个变量赋值时，你才创建了这个变量，变量用于存储值比如数字、文本、字符串或者数组。一旦设置了某个变量，我们就可以在脚本中重复地使用它
  PHP中变量必须使用一个美元符号$，后面跟着变量名来表示，使用赋值操作符(=)给一个变量赋值
  不需要声明变量，但是需要初始化
  初始化 就是给变量初次赋值，或者变量的默认值
  赋值 [=]
  PHP脚本从上到下依次执行
  引用赋值
    $c = &$a(起别名，一块内存空间)

简单的PHP语句
1. phpinfo()
2. echo  用于输出简单得变量
3. var_dump(); 用于输出变量值及其类型 

PHP 语法错误
  Error    结束脚本执行
  Warring  只提示，不影响执行
  Notice

变量的释放
unset()

变量的命名
 以[$]开头
 严格区分大小写
 字母|数字|下划线，不能以数字开头
 尽量不要使用PHP关键字作为变量名

可变变量
```
 $name="hello";
 $$name="World";
 echo $name;
 echo "<br />";
 echo $hello;//$$name
```

变量类型
  布尔类型
    true
    false
    以下内容会被当做false，其他均会被认为true
```
1. 布尔值false
2. 0
3. 浮点型0.0
4. 空白字符和字符串0
5. 没有成员的数组
6. NULL
```
 int型  存储整数
 float  存储小数
 String 字符串
   ''  "" 
   定界符（<<<HTML定界符的开始 HTML;
   定界符的结束）<<< 后面是大写字母 ;
   单引号定义的字符串中的单引号需要转义[\']
   单引号定义的字符串中[$]符号原样输出
   双引号定义的字符串中，[$]符号是变量的开始，变量整体用{}括起来
   单双引号定义的字符串中输入的特殊字符包含['"$...]需要转义
   定界符的开始和结束后面不能有任何字符包括空白和注释

  数组
  对象
  常量
    不变的量
    定义
      define("NAME","GHKI")
    使用
      直接使用即可
    预定义常量
      常量名            常量值
      __FILE__         当前的文件名
      __LINE__         当前行数
      __Function__     当前行数
      __CLASS__        当前的类名
      __METHOD__       当前对象的方法名
      PHP_OS           UNIX或WINNT等
      PHP_VERSION      当前PHP服务器的版本
      DIRECTORY_SEPARATOR   \或/ 根据操作系统决定目录的分隔符

# 运算符
  算数运算符
  逻辑运算符 非! 与and && 或or || 异或xor
    与运算的优先级要高于或运算
  比较运算符 
    比较参与运算的单元是否相同，相同为真，不同为假
    ==
    ===
    >
    >=
    <
    <=
    !=
    !==
    <>
  赋值运算符
    =
    +=
    -=
    *=
    /=
    %=
    .=
    <> 不等于
  其他运算符
    ?:  三元运算符
    `` 将字符串当作命令执行
    @  屏蔽提示，警告
  字符串运算符
    . 拼接
  运算符的优先级

# 流程控制

顺序执行
  PHP代码执行时，依次顺序执行
分支执行
  单向分支
    if(判断条件){执行语句块}
  双向分支
    if(判断条件)(执行语句块)else{语句块2}
  多向分支
    if(判断条件)(执行语句块)elseif(){语句块2}elseif(){}...
    switch
      case
      default
循环执行
  while
    当满足条件时，执行
    计数器，变量
    判断条件
  do ... while
    先执行，再判断
  for
特殊流程控制语句
  break
  break 2;  跳出两层循环
  continue  跳过本次循环
  die()
  exit()    结束脚本

# PHP函数

函数
  代码块
  有输入，有输出
  ```
  function 函数名(形参){
    代码块
    return; //不写，默认返回NULL
  }
  ```
注意：函数调用时，实参要按照顺序给形参
     函数调用时，互相独立，默认没有联系
     执行完毕后，返回调用的位置，继续向下执行

# PHP变量的范围
  局部变量
    在函数内部定义的变量
    变量的作用范围就是这个函数
  全局变量
    在php脚本中，函数外部定义的变量
    变量的作用域为整个PHP脚本

    在函数中使用全局变量
      1. 传参
      2. 声明 global
      3. 常量的作用域，是超全局
  静态变量
    在函数内部定义，并且用static修饰符修饰
    仅在函数初次执行时被初始化

# 参数的传递
  按值传递参数（默认方式）
    对形参的操作，不会对实参产生影响
  引用传参
    相当于跟实参起了一个别名，对形参的操作会对实参产生影响
  默认参数
    如果没有给函数传递实参，取默认值
    建议： 全给默认参数
  可变函数参数列表
    func_num_args(); 传参个数
    func_get_arg(1); 根据参数偏移量，从零开始计数，获取参数
    func_get_args(); 
  可变函数
    函数名为变量，类似结构 $a($b);
    也是最简单的后门
    $a = "system";
    $a("ipconfig"); //函数 函数名为$a  

# 递归函数
  在函数内部自己调用自己
# 内部（内置）函数
  PHP提供许多现成的函数或结构

# 数组
  变量类型
  复合数据类型
  键值对
    键名 键值
    key  value
  数组中的元素
    除了对象，可以存放任意类型得数据
  数组的分类
    键值对 整型的正数  索引数组
    键值对 具有语义的字符串 关联数组
  数组的创建
    第一种创建数组的方式
    $stu[]
    1. 在未指定键名的情况下，给数组赋值，键名从零开始计数，一次增大
    2. 可以手动给键名

    第二种方法
      array()

  数组元素的访问
    1. 读取
    2. 添加
    3. 修改

  数组的遍历
      for  只适用有规律的索引数组
      foreach  语言结构

  二维数组
    
  多维数组

  预定义超全局数组变量
    PHP定义好的，可以直接使用
    函数内部或者外部都能使用

  名称                     作用
  $GLOBALS                 引用全局作用域中可用的全局变量
  $_SERVER                 一个包含了诸如头信息(header)、路径)(path)、以及脚本位置(script locations)等等信息的数组
  $_GET                    通过URL参数传递给当前脚本的变量的数组
  $_POST                   当HTTP POST请求的Content-Type是application/x-www-form-urlencoded multipart/form-data时，会将变量以关联数组形式传入当前脚本
  $_FILES                  通过HTTP POST方式上传到当前脚本的项目的数组
  $_COOKIE                 通过HTTP Cookies方式传递给当前脚本的变量的数组
  $_SESSION                当前脚本可用SESSION变量的数组
  $_REQUEST                默认情况下包含了$_GET,$_POST和$_COOKIE的数组
  $_ENV                    通过环境方式传递给当前脚本的变量的数组

$_GET
http://localhost/PHP/array/get.php?name=AJEST
参数的名        键名
参数的值        键值

$_POST   HTTP请求报文的请求正文中

move_uploaded_file(); 移动上传文件

# 会话控制

浏览网页的时候，使用的是HTTP协议

客户端发出请求 
服务端给出响应

# COOKIE
  COOKIE是存储在客户端的一段文本，文件|字符串
  服务器发给客户端的
  每次客户端浏览器 在发出请求时，都会携带cookie信息

  cookie性质
    name          cookie的名称
    value         cookie的值
    expire        过期时间
    path          cookie的有效路径
    domain        cookie的域名
    secure        https
    httponly      仅仅通过http协议访问 不能通过js访问
  
  设置cookie的语句
  setcookie();

  浏览器cookie信息 f12 存储
  
  接收cookie信息
  $_COOKIE

  COOKIE安全风险
    窃取与欺骗

  session机制（服务器端）
    依赖cookie实现（浏览器端）
    session id
  session_start(); //开启session机制
  $_SESSION        //完成session数据的读写
  session_destory()  //注销session

  