# 产品概述

<Toc />

环信即时通讯为开发者提供高可靠、低时延、高并发、安全、全球化的通信云服务，支持单聊、群聊、聊天室。提供多平台 SDK 支持，包括：Android、iOS、Web；同时，提供 EaseIM 和 EaseIMKit 以及服务端 REST API，帮助开发者快速构建端到端通信的场景。

## 平台架构

![环信 IM 后台](@static/images/product/framework.png)

## 集成概述

在 [环信即时通讯控制台](enable_and_configure_IM.html) 注册和开通服务后，开发者主要需要了解服务器端集成和客户端集成内容。

![img](@static/images/product/integration-overview.png)

服务端集成请看：[环信即时通讯 REST API 概览](/document/server-side/overview.html)。

客户端 Demo 体验请查看：

[Android Demo（EaseIM App）体验](/document/android/demo.html)

[iOS Demo（EaseIM App）体验](/document/ios/demo.html)

客户端集成请查看相应的环信 SDK 开发文档：

[环信即时通讯 IM Android 快速开始](/document/android/quickstart.html)；

[环信即时通讯 IM iOS 快速开始](/document/ios/quickstart.html)；

[环信即时通讯 IM Web 快速开始](/document/web/quickstart.html)。

## 功能概述

用环信即时通讯能实现以下功能：

### 单聊

环信单聊，支持丰富的消息类型，以及离线消息、漫游消息等功能。

### 群聊

环信群聊，支持丰富的消息类型，支持完整的群组管理能力，包含发布群公告、设置群角色等。

### 用户管理

提供用户体系管理能力，如：好友管理、黑名单管理等。支持用户资料存储，包括：头像、昵称、自定义用户信息等。

### 丰富的消息类型

支持单聊/群聊中，发送文本、表情、图片、语音、视频、地理位置、文件，以及红包和礼物等的自定义消息。

### 第三方消息推送

消息推送指当应用在后台运行，或进程被杀时，用户处于离线状态，新消息在发送至环信服务器后，会被转发至第三方推送服务器进行推送，以确保该消息依然可以送达客户端。推送消息在安卓端是使用 Firebase Cloud Message(FCM) 实现，在 iOS 端使用 Apple Push Notification service(APNs) 实现。

### 多端消息同步

环信支持一个账号同时登录多台设备，可实现终端用户的消息通过服务器保存和同步，保证各端均能收发消息同步。

### 消息撤回

消息发出后可以进行消息撤回，提供 SDK 和 REST API 端两种撤回方式。

## 适用场景

环信适用于端到端实时消息沟通的场景：

- 应用内聊天（如：陌生人社交、相亲等）
  - 支持丰富的消息类型、好友关系管理
  - 支持群管理能力、群公告设置、群角色设置等
- 应用内通知
  - 支持广播消息、自定义通知消息等
  - 支持用户管理，包括储存用户信息、用户封禁等
- 视频/语音直播
  - 支持聊天室管理能力
  - 支持丰富类型的聊天室消息，包括弹幕、红包、礼物等
- 企业协作
  - 支持用户管理，设置企业组织架构、好友关系管理
  - 支持群管理能力、群公告设置、群附件发送、群角色设置等
- 买家卖家沟通
  - 支持订单通知、问候语设置、自定义消息发送
  - 支持卖家内部管理、公告设置、成员管理等
- 线上问诊
  - 支持丰富的消息类型，图文病情描述、语音消息等
  - 支持用户信息存储、用户身份管理等

## 产品优势

环信主要有以下优势：

### 全球部署

环信在全球设有五大数据中心、200+ 边缘加速节点，网络服务覆盖全球 200 多个国家和地区。

### 低延时

环信全球平均延时小于 200 毫秒，相同区域平均延时小于 100 毫秒。

### 高并发

环信支持同时在线人数无上限，聊天室亿级消息并发。

### 高可靠性

环信数据中心同城三中心部署，SLA 99.9%。 优异的弱网对抗能力，70% 丢包情况下消息到达率 100%。

### 多平台

环信即时通讯支持以下平台，且平台间能够互通：

- Android 4.4+
- iOS 9.0+
- Web（Internet Explorer 9+、FireFox 10+、Chrome 54+、Safari 6+、IE 9+、Edge 12+、QQ 浏览器 8.0+、360 浏览器 10.0+、Opera 浏览器 58+、微信 H5、App 内嵌 H5）