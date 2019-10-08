<!--
 * @description: 
 * @author: JXY
 * @Date: 2019-10-08 17:08:44
 * @Email: JXY001a@aliyun.com
 * @LastEditTime: 2019-10-08 17:08:44
 -->

<a name="8c0a783d"></a>
## 什么是网络？
所谓网络可以理解为由集线器连接起来的多台计算机，组成一个子网。而无数的子网通过路由器被相互连接起来，进而形成网络。

<a name="f643cbcd"></a>
## 什么是网址？
网址URL(Uniform Resource Locator)，统一资源定位符。通过URL可以获取到指定的资源文件。

<a name="da19f36d"></a>
### URL 组成
![未命名文件 (1).png](https://user-gold-cdn.xitu.io/2019/10/8/16daa6a2e4382d8b?w=1047&h=200&f=png&s=13097)

- protocol： 协议，常见的协议是http，https
- hostname： 主机地址，可以是域名，也可以是IP地址
- port： 端口， http协议默认端口是：80端口，如果不写默认就是:80端口
- path： 路径，网络资源在服务器中的指定路径
- parameter： 参数， 如果要向服务器传入参数，在这部分输入
- query： 查询字符串， 如果需要从服务器那里查询内容，在这里编辑
- fragment： 片段， 网页中可能会分为不同的片段，如果想访问网页后直接到达指定位置，可以在这部分设置

<a name="2bd25ba2"></a>
### URI 与 URL，URN 之间的关系

- URI ：  Universal Resource Identifier  统一资源**标志符**
- URL ： Universal Resource Locator    统一资源**定位符**
- URN ：Universal Resource Name     统一资源**名称**

三者关系图如下：
<a name="6664d365"></a>
![image.png](https://user-gold-cdn.xitu.io/2019/10/8/16daa6a2e4592b79?w=180&h=108&f=png&s=4150)

<a name="2b1f234b"></a>
## IP地址到底是什么

网络是由路由器连接起来的无数个子网组成，而子网由一个个实体的计算机连接组成。数据包能够在网络中传输到指定的某一台计算机上，则需要知道这台计算机所在的**子网号**，即：网络号，以及**主机号**，即：这台计算机在子网中的编号。而IP地址被设计用来存储以上信息。<br />
<br />ip地址是一串32比特的的数字，按照一个字节(8比特)为一组分成4组，使用10进制表示然后用原点分开。但是这样并不知道具体那一部分是主机号，那一部分是网络号。所以由又引入了另一个概念 **子网掩码**，它是一串与IP地址等长度的32比特数字，左边是1，右边是0。子网掩码中为1的部分对应IP地址中相同位置的数字表示网络号，为0的部分对应IP地址中的位置表示主机号。

<a name="7dffe517"></a>
### IP地址与子网掩码之间的关系
![未命名文件 (1).png](https://user-gold-cdn.xitu.io/2019/10/8/16daa6a2e466776a?w=747&h=452&f=png&s=16223)
<a name="4a94236f"></a>
### IP地址表示方法

- IP地址主体表示法：10.11.12.13
- 采用与IP地址主体相同的格式方式表示子网掩码的方法：10.11.12.13/255.255.255.0
- 采用网络比特数来表示子网掩码的方法：10.11.12.13/24
- 表示子网地址：10.11.12.**0**/24，主机号部分全部为0，这个IP地址表示的不是一台单独的计算机，而是整个子网
- 表示子网地址：10.11.12.**255**/24，主机号部分全部为1,这个IP地址表示对整个子网进行广播

<a name="d10560f7"></a>
### 重点总结
**IP地址主机号：全部为0 ,表示整个子网。全部为1,表示向子网上所有设备发送数据包，即：广播**<br />
<a name="215ba179"></a>
## 什么是域名？
首先明确一点，直接使用IP地址是可以正常工作的。由于IP地址是一串32比特的数字，对人来说，很难去记住。例如我们可以轻松的记住某个人的名字，但是记住其电话号码明显要多费点事。同理，域名的存在也是为了我们更方便的去记忆。但是问题来了，为什么不直接用名称来确定通信对象，而非要使用域名呢？原因在于使用名称即：域名，是则需要处理几十个到255个字节的字符，这会增加路由器的负担，传输数据花费更多的时间。

<a name="74c3df45"></a>
## DNS解析
在我们正常的上网过程中很少会见到直接使用IP地址的情况，基本都是在浏览器中输入域名，就可以直接访问到指定网站。但是在网络中发送数据包都必须使用IP地址，那么这个IP地址来自于哪里呢？这里就需要DNS服务来将域名解析为它多对应的IP地址。简单来说就是浏览器询问最近的DNS服务器，'www.xxx.com'的IP地址是多少，随后DNS服务器会将该域名对应的IP地址发送回来。<br />


