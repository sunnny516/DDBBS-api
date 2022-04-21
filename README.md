# DDBBS 社区API

## 前言废话
+ 打造一个简单的纯粹的二刺螈社区,就类似A岛那样的吧
+ 前端是打算开源了,我尝试自己写了个手机段客户端,写的很屎,所以说有大佬可以开发第三方的手机电脑客户端也是可以的


## 注册&登录方法
使用get提交你的账号
```bash
http://dongmanshe.net/sys/auth.php?mode=reg&username=用户名&password=密码
```
服务器返回606 或者 602 即代表账号注册成功


## 获取Token
使用get提交你的账号,获取token,token是账号的主要凭证
```bash
http://dongmanshe.net/sys/auth.php?mode=token&username=用户名&password=密码
```
服务器返回 一串字符则是你的token


## 使用Token获取用户信息
使用get提交你的token
```bash
http://dongmanshe.net//sys/auth.php?mode=token_get&token=你的token
```
服务器返回Json(json以后可能有变化)
```bash
[{
	"uid": "用户ID",
	"name": "用户名",
	"avater": "头像",
	"star": "星星",
	"joining": "注册时间",
	"activetime": "最后活跃时间",
	"Checktime": "签到时间",
	"postend": 最后活动的帖子,
	"token": "你的token"
}]
```





## 瞎编的错误代码
```bash
660  用户名或者密码不能空
601  账号或密码错误
602  用户名已存在
600  登录成功
606  注册成功
661  token不存在
662  token错误
666  系统错误(参数错误)
501  内容不能空
502  内容有违禁词
550  提交成功 
555  图片提交成功
```