# 第三章、IP地址详解

## 一、简单局域网的构成

局域网：一般称为内网 
简单局域网的构成：交换机、网线、PC（其他IT终端） 
交换机：用来组建内网的局域网的设备。

## 二、IP地址

IP地址就是一个唯一标识，是一段网络编码（二进制，下章学习），由32位组成

IP地址形式：X.X.X.X X的范围：0-255

## 三、子网掩码

局域网通信规则：在同一个局域网中，所有的IP必须在同一网段中才可以互相通信！
IP地址构成：网络位+主机位 （网络位相同的IP地址，为同一网段）
子网掩码： 用来确定IP地址的网络位
子网掩码如何确认网络位：与255对应的数字为网络位，与0对应的数字为主机位
 255.0.0.0
 255.255.0.0
 255.255.255.0

如：
10.1.1.1 255.0.0.0 
获知：10.1.1.1属于10.网段，名字叫.1.1.1 

10.1.1.1 255.255.0.0 
获知：10.1.1.1属于10.1.网段，名字叫.1.1 

10.1.1.1 255.255.255.0 
获知：10.1.1.1属于10.1.1网段，名字叫.1

注意：1个IP地址，必须配套一个子网掩码

## 四、IP地址详解

国际标准组织ISO定义地址分类：五大类 （是以IP地址的第一位进行区分的）
A类： 1-126 默认子网掩码：255.0.0.0
B类： 128-191 默认子网掩码：255.255.0.0
C类： 192-223 默认子网掩码：255.255.255.0
D类： 224-239 组播地址
E类： 240-254 科研使用

注：
1. 目前我们可以使用的只有A、B、C3类 
2. ABC3类的子网掩码可以修改！

### IP地址详细解剖：

案例1：
10.1.1.1
255.255.255.0
问：10.1.1.1属于哪个网段？所在网段有多少个可用的IP地址？该网段的广播地址是什么？
答：
10.1.1.1属于10.1.1.0网段。
10.1.1.0网段可用的IP地址范围：10.1.1.1-10.1.1.254
10.1.1.0网段的广播地址：10.1.1.255

案例2：
10.1.1.1
255.255.0.0
10.1.1.1属于哪个网段？所在网段有多少个IP地址？该网段的广播地址是什么？
答：
10.1.1.1属于10.1.0.0网段。
10.1.0.0网段可用的IP地址范围：10.1.0.1-10.1.255.254（65534）
10.1.1.0网段的广播地址：10.1.255.255

总结：当主机位全部置0代表网段，主机位全部置255代表该网段的广播地址

## 七、配置IP地址