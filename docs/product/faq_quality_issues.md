# 质量类问题

<Toc />

## 如何排查 环信即时通讯 IM 单聊消息丢失

### 问题描述

在使用 环信即时通讯 IM 聊天的过程中，如果遇到用户 A 给用户 B 发消息，用户 B 没有接收到的情况(视为消息丢失)，可以按照下面的说明进行排查。

### 问题原因

可能是以下原因：

- 用户 A 消息发送失败；
- 接受消息的用户 ID 错误；
- 用户 B 把 A 设为黑名单了；
- 用户 B 在其他设备上登录时接收了消息；
- 用户 B 离线消息数量超过 500 条等。

### 排查方案

#### 一、APP 未上线时，在使用环信即时通讯 IM SDK 集成阶段测试用户出现消息丢失

分为用户 B 在线和不在线两种情况：

- 用户 B 在线的情况下收不到用户 A 发的消息：
    1. 检查用户 A 发送的消息是否成功，可以根据 SDK 发消息方法返回的结果判断消息是否发送成功，如果发送失败，则用户 B 收不到消息。
    2. 检查用户 A 给用户 B 发消息时，B 的 ID 是否正确，如果传的不是用户 B 的 环信即时通讯 IM ID，那么用户 B 收不到消息。
    3. 检查用户 B 是否将用户 A 加入黑名单 ，如果用户 B 将用户 A 加入黑名单，那么用户 B 将收不到用户 A 发的消息，详见 [获取黑名单](/document/server-side/user_relationship.html#获取黑名单)。
- 用户 B 不在线时，用户 A 给用户 B 发消息，用户 B 重新登录后收不到消息：
    1. 可能存在用户 B 有在其他设备上登录的情况，把消息接收走了，所以在当前设备登录时将不再接收消息。
    2. 确认用户 B 的离线数量是不是很大，如果超过 500 条，那么用户 B 只会收到最新的 500 条消息，超过500条的那部分消息将接收不到。

#### 二、APP 已经上线后，线上用户出现消息丢失

1. 先与自己的客户确认是否存在 “用户 B 不在线时，用户 A 给用户 B 发消息，用户 B 重新登录后收不到消息”下描述的 1，2 两种情况。
2. 提供 App Key、环信即时通讯 IM ID、丢失的消息内容和发送消息的时间，然后登录环信即时通讯云控制台，提交工单，让环信即时通讯 IM 的技术支持排查。[环信即时通讯云控制台](https://console.easemob.com/user/login)）。

## 排查环信即时通讯 IM 群聊消息丢失

### 问题描述

用户有时反馈环信即时通讯 IM 丢消息，在用户 A 与用户 B 在同一个群组，用户 A 向群组中发消息这种情况下，我们建议先按以下步骤自查。如果没发现问题，可以提交工单由技术支持同事协助排查。

### 问题原因

可能的原因包括用户 A 构建消息时传的消息类型不是群聊类型、用户 A 消息发送失败、用户 B 不在群组中、用户 B 屏蔽了该群组消息、用户 B 被加入了群组黑名单、用户 B 在其他设备上登录时接收了消息以及用户 B 群组离线消息数量超过 200 条等。

### 排查方案

#### 一、APP 未上线时，使用环信即时通讯 IM SDK 集成阶段测试用户出现消息丢失

- 用户 B 在线的情况下收不到用户 A 发的群组消息：
    1. 检查用户 A 在构建消息时，传的消息类型是不是群聊类型的，如果不是则用户 B 收不到用户 A 发的群组消息，详见 [Android 版构建消息](/document/android/message_send_receive.html#发送文本消息) 或 [iOS 版构建消息](/document/ios/message_send_receive.html#发送文本消息)。
    2. 检查用户 A 发送的消息是否成功，可以根据 SDK 发消息方法返回的结果判断消息是否发送成功，如果发送失败，则用户 B 收不到用户 A 发送的群组消息。
    3. 检查用户 A 给用户 B 发消息时，传的群组 ID 是否正确(是否为 A 与 B 共同加入的群组 ID)，如果传的不是正确的群组 ID，那么用户 B 收不到消息用户 A 发的群组消息。
    4. 检查用户 B 是否在群组中，可以获取群组详情，看群组中是否有用户 B，详见 [获取群组详情](/document/server-side/group.html#获取群组详情)。
    5. 检查用户 B 是否屏蔽了该群组消息，如果用户 B 屏蔽了该群组消息，那么将收不到用户 A 发的群组消息，详见 [Android 屏蔽和解除群消息](/document/android/group_manage.html) 或 [iOS 屏蔽和解除群消息](/document/ios/group_manage.html)。
    6. 检查用户 B 是否被加入了群组黑名单，如果用户 B 被加入到了群组黑名单，那么将收不到用户 A 发的群组消息，详见 [获取群组黑名单](/document/server-side/group.html#查询群组黑名单)。
- 用户 B 不在线时，用户 A 向群组中发送消息，用户 B 重新登录后收不到群组消息：
    1. 可能存在用户 B 在其他设备上登录把消息接收走了的情况，则在当前设备登录时将不再接收消息。
    2. 确认用户 B 所在的群组的离线数量是不是很大，如果超过200条，那么用户 B 只会收到最新的 200 条群组消息，超过 200 条的那部分群组消息将接收不到。

#### 二、App 已经上线后，线上用户出现群组消息丢失

1.先与 APP 的用户确认是否存在：‘用户 B 在线的情况下收不到用户 A 发的群组消息’的 3、4 和 5 三种情况, 以及’用户 B 不在线时，用户 A 向群组中发送消息，用户 B 重新登录后收不到群组消息下描述的 1 和2 两种情况。

2.若排除以上情况，可根据 App Key、发送者 ID 或消息 ID、消息发送时间在 [环信即时通讯云控制台](https://console.easemob.com/user/login) 自行查询消息投递状态，具体操作如下：

1. 登录环信即时通讯云控制台。
2. 在首页的 应用列表 区域中，点击具体应用的 **操作** 栏中的 **查看**。
3. 在界面左侧导航栏中选择**应用详情**下的**即时通讯** > **实时查询** > **IM消息投递查询**。

![img](@static/images/product/faq-msgdeliveryquery.png)

## 参考

### 如何判断用户是否在线

在使用环信即时通讯 IM 基础聊天业务的场景下，处理特定业务需求时需知晓某些用户是否在线。为此，环信即时通讯 IM 提供单个用户以及批量用户是否在线状态的查询，详见 [用户在线状态回调](/document/server-side/user_status_callback.html)。

除此之外，可以在 [环信即时通讯云控制台](https://console.easemob.com/user/login) 上查询用户连接状态，具体操作如下：

1. 登录环信即时通讯云控制台。
2. 在首页的 **应用列表** 区域中，点击具体应用的 **操作** 栏中的 **查看**。
3. 在界面左侧导航栏中选择 **应用详情** 下的 **即时通讯** > **实时查询** > **IM用户连接状态**。

![img](@static/images/product/faq-userconnectionstatus.png)

说明: 环信即时通讯 IM SDK 未提供直接查询用户是否在线的方法，客户端可以封装查询用户是否在线的接口调用或者让自己服务器端来调用再与自己客户端交互。