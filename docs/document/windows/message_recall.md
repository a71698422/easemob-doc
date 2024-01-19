# 撤回消息

<Toc />

发送方可以撤回一条发送成功的消息，包括已经发送的历史消息，离线消息或漫游消息。

默认情况下，发送方可撤回发出 2 分钟内的消息。你可以在[环信即时通讯云控制台](https://console.easemob.com/user/login)的**功能配置** > **功能配置总览** > **基础功能**页面设置消息撤回时长，该时长不超过 7 天。

## 技术原理

环信即时通讯 IM 通过 `IChatManager` 和 `Message` 类支持你撤回一条发送成功的消息：

- `RecallMessage`：撤回一条发送成功的消息。

## 前提条件

开始前，请确保满足以下条件：

- 完成 SDK 初始化，详见 [快速开始](quickstart.html)。
- 了解环信即时通讯 IM 的使用限制，详见 [使用限制](/product/limitation.html)。

## 实现方法

### 撤回消息

你可以调用 `RecallMessage` 方法撤回一条发送成功的消息。

调用该方法后，服务端的该条消息（历史消息，离线消息或漫游消息）以及消息发送方和接收方的内存和数据库中的消息均会被移除，消息的接收方会收到 `OnMessagesRecalled` 事件。

```csharp
SDKClient.Instance.ChatManager.RecallMessage("Message ID", new CallBack(
  onSuccess: () => {
    Debug.Log("回撤成功");
  },
  onProgress: (progress) => {
    Debug.Log($"回撤进度 {progress}");
  },
  onError: (code, desc) => {
    Debug.Log($"回撤失败，errCode={code}, errDesc={desc}");
  }
 ));
```

### 设置消息撤回监听

你可以使用 `IChatManagerDelegate` 设置消息撤回监听，通过 `OnMessagesRecalled` 事件监听发送方对已接收的消息的撤回。

```csharp
void OnMessagesRecalled(List<Message> messages);
```