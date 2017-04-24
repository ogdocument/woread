# 沃阅读接口文档

[TOC]

## 中转服务器

http://xxx.xxx.xxx.xxx:8080/woread/100

## 提交方式

支持 GET & POST

## 全 Http 支付方式

### 支付流程

1. 获取验证码
2. 发送支付请求

### 接口

#### 获取验证码

- REQUEST

| 名称 | 参考 | 说明 |
| - | - | - |
| reqtype | http | 说明采用 http 扣费方式 |
| step | verify | 获取取验证码 |
| paycode | 00000002XXX7 | - |
| usercode | 156XXXX1036 | 手机号 |
| channelid | 1XXX72 | 

- RESPONE

| 名称 | 参考 | 说明 |
| - | - | - |
| url | - | 提交给官方服务器URL |
| method | get | 提交给官方服务器方式 |
| content | 00000002XXX7 | 提交给官方服务器加密后的内容 |

#### 发送支付请求

- REQUEST

| 名称 | 参考 | 说明 |
| - | - | - |
| reqtype | http | 说明采用 http 扣费方式 |
| step | pay | 支付请求 |
| gamename | 天天XX | 游戏名称 |
| smscode | 255809 | 上一步返回的验证码（在短信中获取） |
| usercode | 156XXXX1036 | 手机号 |
| channelid | 1XXX72 | - |
| myid | 1234 | - |
| appid | ttXX | - |
| paycode | 00000002XXX7 | - |
| orderid | 0000000000003 | 自定义13位订单号（注意，完整订单号不是13位，   <br />只有13位是可以自定义的） |
| productdesc | 复活 | 物品描述 |
| idx | 0 | **物品的注册索引号** |

- RESPONE

| 名称 | 参考 | 说明 |
| - | - | - |
| url | - | 提交给官方服务器URL |
| method | post | 提交给官方服务器方式 |
| content | 00000002XXX7 | 提交给官方服务器加密后的内容 **需要 URL DECODE 后，再提交给联通** |
