# 消息表情回复 Flutter

<Toc />

环信即时通讯 IM 提供消息表情回复（下文统称 “Reaction”）功能。用户可以在单聊和群聊中对消息添加、删除表情。表情可以直观地表达情绪，利用 Reaction 可以提升用户的使用体验。同时在群组中，利用 Reaction 可以发起投票，根据不同表情的追加数量来确认投票。

注意：目前 Reaction 仅适用于单聊和群组。聊天室暂不支持 Reaction 功能。

## 技术原理

环信即时通讯 IM SDK 支持你通过调用 API 在项目中实现如下功能：

- `addReaction` 在消息上添加 Reaction；
- `removeReaction` 删除消息的 Reaction；
- `fetchReactionList` 获取消息的 Reaction 列表；
- `fetchReactionDetail` 获取 Reaction 详情；

Reaction 场景示例如下：

![](@static/images/ios/reactions.png)

分别展示如何添加 Reaction，群聊中 Reaction 的效果，以及查看 Reaction 列表。

## 前提条件

开始前，请确保满足以下条件：

1. 完成 `1.0.5 以上版本` SDK 初始化，详见 [快速开始](quickstart.html)。
2. 了解环信即时通讯 IM API 的 [使用限制](/product/limitation.html)。
3. 已联系商务开通 Reaction 功能。

## 实现方法

### 在消息上添加 Reaction

调用 `addReaction` 在消息上添加 Reaction，在 `onMessageReactionDidChange` 监听事件中会收到这条消息的最新 Reaction 概览。

示例代码如下：

```dart
// reaction: Reaction ID
// msgId: 消息 ID
// 在指定消息上添加 Reaction
ChatClient.getInstance()
  .chatManager.addReaction(reaction, msgId)
  .then((result) => {
    console.log("success: ", result);
  })
  .catch((error) => {
    console.log("fail: ", error);
  });
```

### 删除消息的 Reaction

调用 `removeReaction` 删除消息的 Reaction，在 `onMessageReactionDidChange` 监听事件中会收到这条消息的最新 Reaction 概览。

示例代码如下：

```dart
try {
  await EMClient.getInstance.chatManager.addReaction(
    messageId: messageId,
    reaction: reaction,
  );
} on EMError catch (e) {
}
```

### 获取消息的 Reaction 列表

调用 `getReactionList` 可以从服务器获取指定消息的 Reaction 概览列表，列表内容包含 Reaction 内容，用户数量，用户列表（概要数据，即前三个用户信息）。
对应消息 `EMMessage` 有便捷的访问方式 `reactionList`。
示例代码如下：

```dart
try {
  Map<String, List<EMMessageReaction>> map =
      await EMClient.getInstance.chatManager.fetchReactionList(
    messageIds: messageIds,
    chatType: ChatType.GroupChat,
    groupId: groupId,
  );
} on EMError catch (e) {
}
```

消息的快捷访问方式。示例如下：

```dart
try {
    List<EMMessageReaction> reactions = await msg.reactionList();
}on EMError catch (e) {
}
```

### 获取 Reaction 详情

调用 `fetchReactionDetail` 可以从服务器获取指定 Reaction 的详情，包括 Reaction 内容，用户数量和全部用户列表。示例代码如下：

```dart
try {
  EMCursorResult<EMMessageReaction> result =
      await EMClient.getInstance.chatManager.fetchReactionDetail(
    messageId: messageId,
    reaction: reaction,
  );
} on EMError catch (e) {
}
```

### 管理 Reaction 监听

```dart
// 监听 Reaction 更新
class _ChatPageState extends State<ChatPage> {
  @override
  void initState() {
    super.initState();
    EMClient.getInstance.chatManager.addEventHandler(
      "UNIQUE_HANDLER_ID",
      EMChatEventHandler(
        onMessageReactionDidChange: (list) => {},
      ),
    );
  }

  @override
  void dispose() {
    EMClient.getInstance.chatManager.removeEventHandler("UNIQUE_HANDLER_ID");
    super.dispose();
  }
}
```