<div style="text-align: center">
<h1>文件快递柜</h1>
<p><em>匿名口令分享文本，文件，像拿快递一样取文件</em></p>
</div>

---

[简体中文](./readme.md) | [English](./readme_en.md)

## 主要特色

- [x] 轻量简洁：Fastapi+Sqlite3+Vue2+ElementUI
- [x] 轻松上传：复制粘贴，拖拽选择
- [x] 多种类型：文本，文件
- [x] 防止爆破：错误次数限制
- [x] 防止滥用：IP限制上传次数
- [x] 口令分享：随机口令，存取文件，自定义次数以及有效期
- [x] 匿名分享：无需注册，无需登录
- [x] 管理面板：查看所有文件，删除文件
- [x] 一键部署：docker一键部署

## 预览

### 寄件

<table style="width: 100%">
<tr style="width: 100%">
<td style="width: 50%">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_1.png" alt="寄文件">
</td>
<td style="width: 50%">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_2.png" alt="寄文本">
</td>
</tr>
<tr style="width: 100%;">
<td colspan="2" style="width: 100%;">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_3.png" alt="寄文本">
</td>
</tr>
</table>

### 取件

<table style="width: 100%">
<tr style="width: 100%">
<td style="width: 50%">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_6.png" alt="取件">
</td>
<td style="width: 50%">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_5.png" alt="取件码错误">
</td>
</tr>
<tr style="width: 100%;">
<td colspan="2" style="width: 100%;">
<img src="https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_4.png" alt="取文件">
</td>
</tr>
</table>

### 管理

![管理](https://raw.githubusercontent.com/vastsa/FileCodeBox/master/images/img_7.png)

## 部署方式

### Docker一键部署

```bash
docker run -d --restart=always -p 12345:12345 -v /opt/FileCodeBox/:/app/data --name filecodebox lanol/filecodebox:latest
```

### 其他方式

请参考->[部署文档](https://www.yuque.com/lxyo/work/zd0kvzy7fofx6w7v)

## 配置文件

如果需要修改配置，可以将该文件放在`/opt/FileCodeBox/`目录下，并命名为`.env`，然后重启容器即可。

```bash

```dotenv
# 端口
PORT=12345
# Sqlite数据库文件
DATABASE_URL=sqlite+aiosqlite:///database.db
# 静态文件夹
DATA_ROOT=./static
# 静态文件夹URL
STATIC_URL=/static
# 错误次数
ERROR_COUNT=5
# 错误限制分钟数
ERROR_MINUTE=10
# 上传次数
UPLOAD_COUNT=60
# 上传限制分钟数
UPLOAD_MINUTE=1
# 管理地址
ADMIN_ADDRESS=admin
# 管理密码
ADMIN_PASSWORD=admin
# 文件大小限制，默认10MB
FILE_SIZE_LIMIT=10
# 网站标题
TITLE=文件快递柜
# 网站描述
DESCRIPTION=FileCodeBox，文件快递柜，口令传送箱，匿名口令分享文本，文件，图片，视频，音频，压缩包等文件
# 网站关键词
KEYWORDS=FileCodeBox，文件快递柜，口令传送箱，匿名口令分享文本，文件，图片，视频，音频，压缩包等文件
# 存储引擎
STORAGE_ENGINE=filesystem
```
