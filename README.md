# [qsign](https://github.com/fuqiuluo/unidbg-fetch-qsign)共享签名服务器列表

| 签名服务器地址 | 秘钥 Key | 配置 | 地区 | 搭建方式 | 版本/协议版本 | 共享方/联系方式/留言 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| https://qsign.pueh.cc/ | keykeykey114514 | 8h16g | 大陆 | jvm | 1.1.6/8.9.70 | 轻虐 |

❗️注意: 使用他人搭建的服务可能会泄露以下信息：
- 登录账号
- 登录时间
- 登录后发送的消息内容
- 登录后发送消息的群号/好友ID

✅ 不会泄露的信息：
- 账号密码
- 账号 session
- 群列表/好友列表
- 接收的消息
- 除发送消息外的任何历史记录


## 部署方法

Github Wiki: https://github.com/fuqiuluo/unidbg-fetch-qsign/wiki

### Docker部署教程（by [@XZhouQD](https://github.com/XZhouQD)）

` docker run -d --restart=always --name qsign -p 8080:8080 -e ANDROID_ID={android_id} xzhouqd/qsign:8.9.63 `
运行命令之后，用 `docker container ls -a` 查看一下容器是否跑起来，没跑起来的（状态是Exited (1)）用 `docker container logs qsign` 看一下是不是没填**android_id**！

## 自编译qsign方法
要编译[qsign](https://github.com/fuqiuluo/unidbg-fetch-qsign)，需要 `JDK 8` 和互联网连接

首先克隆[qsign存储库](https://github.com/fuqiuluo/unidbg-fetch-qsign)，从终端运行 `./gradlew build` ，然后可以在目录 `build/distributions` 中找到已编译的 tar 或 zip 文件

要获取完整的任务列表，请运行 `./gradlew tasks`

## 小提示 Tips

有些风控等级较高的账号，登录过后1-2天，即使加了签名服务器也会发群消息屏蔽，这时候就要删掉 `session.token` 和 `device.json` 重新登录，重新登录成功后即可再次发送群消息（反复循环）