第三方企业后台
==============

使用[tornado异步框架](http://www.tornadoweb.org)构建一款适用于企业内部运营管理和设备监控的服务器后台。


## 准备工作

1. 注册成为[IntoYun开发者](https://www.intoyun.com)，进行企业认证后，在__授权管理__中提交`服务器授权申请`。


## 开发依赖

- tornado(v4.5.2)

为了从IntoYun平台获取设备的实时数据并通过websocket协议推送到浏览器端, 我们需要安装如下的依赖
- pip install pycrypto
- pip install kafka-python
- pip install futures (for python2)

如果你不想使用Cookie保存用户登录的信息，那么可以设置session存放到Redis中(可选，非必须)
- redis(v3.2)


## 测试数据
- 我们假设企业服务器使用"192.168.0.46"这个IP, 如果有需要，请修改相应的配置文件(config.system)和测试脚本(test目录)的服务器IP。

- HTTP
    我们提供了基于[postman](https://www.getpostman.com/) 的测试数据，导入test目录中的测试集(postman_collection.json)和测试环境变量(postman_environment.json)即可。请求地址: `http://{{host}}:{{port}}/manager`

- Websocket
    我们提供了一个基于nodejs的websocket测试客户端，需要依赖ws库。请求地址: `ws://{{host}}:{{port}}/websocket`
    - npm install --save ws

## TODO
- 异步获取数据库
- 存储设备数据