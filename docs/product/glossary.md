# 术语表

<Toc />

## A

## B

## C

## D

### 单聊

单聊即一对一聊天，支持全类型消息。参与聊天的双方可以是好友也可以是陌生人。

## E

## F

### 封禁用户

禁止用户使用环信即时通讯 IM 服务， 封禁后，用户无法连接环信即时通讯 IM 服务器。

## G

### 广播消息

广播消息是指通过 Rest API 对应用内的所有用户发送消息。当用户离线时，消息会自动转换为系统离线推送。

## H

### 环信即时通讯 IM SDK

环信即时通讯 IM SDK 是环信提供的用于实现即时通讯，比如：单聊、群聊、聊天室的 SDK。

### 环信即时通讯 IMKit

IMKit 是环信即时通讯 IM SDK 的一个开源 UI 组件，提供应用内聊天的常用页面和 UI 组件，帮助开发者快速构建应用的 UI。

### 环信即时通讯 CallKit

CallKit 是环信即时通讯 IM SDK 的一个开源 UI 组件，提供应用内聊天中音视频通话的页面和 UI 组件，帮助开发者快速构建应用的 UI。

### 环信通讯云控制台 （Easemob Console)

环信通讯云控制台是环信提供给开发者管理环信各项服务的工具。

### 会话

会话是一个单聊、群聊或者聊天室所有消息的集合。用户需在会话中发送消息或查看历史消息，还可进行会话置顶、清空聊天记录等操作。

### 会话列表

会话列表是指会话依照一定顺序排列的列表，会话的排列顺序依赖于置顶、会话中最近一条消息的接收时间等因素。

## I

## J

## K

## L

### 聊天室

聊天室是支持多人加入的组织。聊天室中的成员没有固定关系，用户离线后，超过 5 分钟会自动退出聊天室。聊天室成员在离线后，不会收到推送消息。聊天室可以应用于直播、消息广播等。

### 聊天室黑名单

聊天室创建者和管理员可以将聊天室成员加入黑名单，被加入聊天室黑名单的用户不能在聊天室中发送消息。

### 聊天室白名单

聊天室创建者和管理员可以将聊天室成员加入白名单，在聊天室开启全局禁言的情况下，只有白名单中的用户可以在聊天室中发送消息。

### 聊天室创建者

聊天室的创建者，在聊天室中拥有最高权限。可以指定管理员、解散聊天室、更改聊天室信息、对聊天室成员进行管理。

### 聊天室管理员

由聊天室所有者授权，协助进行管理，拥有一定管理权限。可以对聊天室成员进行管理。

### 聊天室成员

聊天室的普通成员，不具备聊天室管理权限。

### 离线消息

当接收方不在线时，环信即时通讯 IM 服务器会暂时保存消息，用户上线时，会接收到服务器保存的离线消息。不同套餐版本的离线消息保存时长不同。单聊和群聊支持离线消息，聊天室不支持离线消息。

### 离线

离线是指用户成功登出环信即时通讯 IM 系统或与环信即时通讯 IM 系统断开连接后的状态。用户登出环信即时通讯 IM 系统之后，无法发送和接受消息，在下次登录后可以接收到离线消息。

### 历史消息（聊天历史记录）

环信即时通讯 IM 服务器会保存历史消息以供查询。开发者可以通过 REST API 下载历史消息压缩包文件。

## M

### 漫游消息

多端登录时，用户在其中一端发送的消息会同步到所有其他客户端，此类消息称为漫游消息。

## N

## O

## P

## Q

### 群组

群组是支持多人沟通的即时通讯系统，成员关系相对稳定。所有群成员可在群中收发送消息。当群成员离线时，可以收到推送消息。群组分为公开群和私有群，公开群可以被搜索到，非群成员可以加入；私有群不能被搜索到，需要群主或群管理员添加非群成员进入。群组成员支持多种角色：群主、群管理员、群成员。群组提供丰富的管理能力，如：群组禁言、群公告、群文件等。

### 群组黑名单

群组创建者和管理员可以将群组成员加入黑名单，加入群黑名单的用户不能在群中发送消息。

### 群组白名单

群组创建者和管理员可以将群组成员加入白名单，在群组开启全局禁言的情况下，只有白名单中的用户可以在群组中发送消息。

### 群组创建者

群组的创建者，在群组中拥有最高权限。可以指定管理员、解散群组、更改群组信息以及对群组成员进行管理。

### 群管理员

由群组所有者授权，协助进行管理，拥有一定管理权限。可以对群组成员进行管理。

### 群成员

群组的普通成员，不具备群组管理权限。

## REST 接口

环信即时通讯 IM 的服务器端接口都是通过 REST 服务方式提供的，REST API 基于最简单的 HTTP 协议，在各个编程语言中都提供了良好的支持。

环信即时通讯 IM REST 平台提供一个多租户用户体系，资源以集合（Collection）的形式描述，这里的 Collection 包括 Database、企业（orgs）、应用（apps）、Chat 用户（users）、群组（chatgroups）、消息（chatmessages）和文件（chatfiles）等等。

## S

### 视频消息

消息内容为视频文件的 URL 地址、时长、大小、格式等信息，默认支持 10 MB。

## T

### 推送

推送是指当应用被杀死时，通过厂商推送接收消息。iOS 设备使用苹果的 APNs（Apple Push Notification service）推送服务、Android 设备为谷歌 FCM（Firebase Cloud Messaging）推送服务。

### 图片消息

图片消息内容属于附件类型消息，内容图片 URL 地址、尺寸、图片大小等信息。最大支持 10 MB。

### 透传消息

透传消息可视为一条指令，通过发送这条指令给对方，通知对方要执行的操作，对方收到消息可自定义处理。（透传消息不会存入本地数据库中，在 UI 上不显示，也不计入未读消息）。具体功能可以根据自身业务需求自定义，例如实现头像或昵称的更新等。

## U

### UUID

即时通讯服务器为 App Key 内用户创建的唯一 ID，不同于用户 ID。

## V

## W

### 文本消息

消息内容是普通文本，其中可以包括超链接，客户端收到消息后存入数据库、计入未读消息数。表情消息为开发者自定义。实质上是发文本消息。接收方收到文本消息后，首先查询文本消息是否是表情消息，如果是，则显示该文本消息为对应的表情图片。

### 位置消息

消息内容为地理位置标题、经度和纬度信息。

### 文件消息

消息内容为文件的 URL 地址、大小、格式等信息，格式不限，默认支持 10 MB。

## X

### 消息回调

消息回调，即聊天服务器会在事件发生之前或之后，向客户的应用服务器发送请求，应用服务器可据此进行必要的数据同步，或者根据业务需求干预事件的后续处理流程。

### 消息云存储

将用户发送的单聊、群聊、聊天室消息存储到聊天服务器，方便用户在更换设备或删除本地消息后，通过服务端获取历史消息，默认单群聊消息服务端最多保存 6 个月，聊天室消息最多保存 2 个月。

### 消息自定义扩展

当基础的消息类型不满足需求时，可以使用消息自定义扩展增强基础消息类型。
使用扩展后，消息大小不能超过原类型消息的大小。
消息自定义扩展的使用场景：例如消息中需要携带被回复的消息内容。
消息自定义扩展作为消息内容会存入本地数据库。

### 消息表情回复 Reaction

在单聊和群聊中对消息添加、删除表情。表情可以直观地表达情绪，利用 Reaction 可以提升用户的使用体验。同时在群组中，利用 Reaction 可以发起投票，根据不同表情的追加数量来确认投票。

## Y

### 用户属性

用户属性指用户的信息，如用户昵称、头像、邮箱、电话、性别、签名、生日等。
比如：在招聘场景下，利用用户属性功能，可以存储性别、邮箱、用户类型（面试者）、职位类型（web 研发）等。当查看用户信息时，可以直接查询服务器存储的用户属性信息。

### 语音消息

语音数据属于附件类型，需要提供时长信息，以秒为单位。最大支持 10 MB。

### 用户 ID

同 username，是 App Key 内用户的唯一标识，不同于即时通讯系统服务器为用户创建的 uuid。

### 用户黑名单

用户将不会接收黑名单中用户发送的消息。

## Z

### 自定义消息

发者自定义的消息类型，例如红包消息、石头剪刀布等形式的消息。

### 在线状态订阅

用户在线状态（即 Presence）包含用户的在线、离线以及自定义状态。即时通讯服务提供发布、订阅和查询用户的在线状态的功能。

### 子区

子区是建立在群组内一条消息上的支持多人沟通的即时通讯系统，子区成员是群组成员的子集。

### 子区消息

子区消息是发生在子区内的消息。