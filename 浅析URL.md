## URL 包含哪几部分，每部分分别有什么作用?
URL包含：协议+域名/IP+端口号+路径+查询字符串+锚点
~~~html
https://www.baidu.com/s?wd=hello&rsv_spt=1#5
协议https  域名/IP：www.baidu.com   路径/s（问号之前）  查询参数 wd=hello&rsv_spt=1  锚点#5    
~~~

## DNS 的作用是什么，nslookup 命令怎么用?
DNS的作用是：把域名和IP对应起来
nslookup +域名 可以得到域名对应的所有IP
~~~html
λ nslookup baidu.com
服务器:  UnKnown
Address:  211.162.52.205

非权威应答:
名称:    baidu.com
Addresses:  220.181.38.148
          39.156.69.79
~~~

* 一个域名可以对应不同的IP，像上面的百度就对应了两个IP，这个叫做均衡负载，防止一台机器扛不住。一般是大公司会这么做。

* 一个IP可以对应不同的域名，这个叫做共享主机，主要是穷的开发者会这么做。
<br>

## IP 的作用是什么，ping 命令怎么用？
IP全称：Internet Protocol网际互连协议
* 定位一台设备
* 封装数据报文，以跟其他设备交流
<br>

### ping+域名 可以得到你所在区域域名对应的IP（
* 如果该域名对应多个IP，ping命令只会显示你所在设备访问该域名时对应的IP，而不会显示所有IP
* nslookup命令则会显示该域名的所有IP
~~~
λ ping baidu.com

正在 Ping baidu.com [220.181.38.148] 具有 32 字节的数据:
来自 220.181.38.148 的回复: 字节=32 时间=60ms TTL=46
来自 220.181.38.148 的回复: 字节=32 时间=100ms TTL=46
来自 220.181.38.148 的回复: 字节=32 时间=51ms TTL=46
来自 220.181.38.148 的回复: 字节=32 时间=84ms TTL=46

220.181.38.148 的 Ping 统计信息:
    数据包: 已发送 = 4，已接收 = 4，丢失 = 0 (0% 丢失)，
往返行程的估计时间(以毫秒为单位):
    最短 = 51ms，最长 = 100ms，平均 = 73ms
~~~
<br>

## 域名是什么，分别哪几类域名?
域名就是对IP的别称，域名和IP通过DNS对应起来
* 一个域名可以对应不同的IP，像上面的百度就对应了两个IP，这个叫做均衡负载，防止一台机器扛不住。一般是大公司会这么做。

* 一个IP可以对应不同的域名，这个叫做共享主机，主要是穷的开发者会这么做。
<pr>

* github.com是二级域名（俗称一级域名）
* username.github.com是三级域名（俗称二级域名） 是github.com的子域名，github.com把子域名给注册用户使用


## 端口port
每种网络的服务功能都不相同，因此有必要将不同的封包送给不同的服务来处理，当你的主机同时开启了FTP与HTTP服务时，别人送来的资料封包，就会依照 TCP 上面的 port 号码来给 FTP 这个服务或者是 HTTP 这个服务来处理。
* HTTP服务默认端口为80
* HTTPS服务默认端口为443
* FTP服务默认端口为21