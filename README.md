# Arma3RedisExtension
一个快速上手的redis扩展

在服务端初始化后首先连接redis服务器
参数: [ip,端口,密码]
redis有密码:
```cpp
"ArmaMapsExt_x64" callExtension ["connectRedis",["127.0.0.1","6379","123456"]]
```
redis无密码:
```cpp
"ArmaMapsExt_x64" callExtension ["connectRedis",["127.0.0.1","6379"]]
```
储存一个字符串至redis缓存服务器
参数:[key,value]

缓存无限期:
```cpp
"ArmaMapsExt" callExtension ["sendMsg",["usename","小明"]]
```
缓存有限期(单位:秒):
```cpp
"ArmaMapsExt" callExtension ["sendMsg",["usename","小明","60"]]
```

从key中获取一个缓存字符串
参数:[key]
```cpp
_data = "ArmaMapsExt" callExtension ["getMsg",["username"]]
```
如果命中缓存则返回值，否则返回空字符串

注意:全程只能在服务器上执行! 模组也只能服务器挂载
