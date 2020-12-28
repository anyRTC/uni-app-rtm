# uni-app-rtm
anyRTC实时消息uni-app插件demo

# anyRTC 实时消息SDK

anyRTC实时消息 包含点对点消息、频道消息、呼叫邀请等功能，适用于在线教育、直播、社交等场景。 本插件提供实时消息能力，支持Android、iOS。

#### 跑通代码需要自定义基座，并且使用iOS和安卓真机运行

#### 概要

* anyRTC音视频品质首选，每月免费赠送1万分钟实时音频；
* anyRTC提供rtm服务，轻松实现交互逻辑；
* 为了帮助中小企业在音视频领域轻松打造爆款应用，详情[anyRTC创业扶持计划。](https://www.anyrtc.io/activity)

#### 快速集成


* 下载示例工程，前往[anyRTC官网](https://www.anyrtc.io)注册账号

* 创建应用，获取应用的App ID。

![appid](https://vkceyugu.cdn.bspapp.com/VKCEYUGU-aliyun-xc5d868hqlyo335e89/1c346660-4656-11eb-8ff1-d5dcf8779628.png)

* 下载插件示例工程，制作自定义基座，主要步骤如图，证书问题，请参照申请证书说明。

![自定义基座](https://vkceyugu.cdn.bspapp.com/VKCEYUGU-aliyun-xc5d868hqlyo335e89/e7b28eb0-4657-11eb-8ff1-d5dcf8779628.png)

* 运行自定义基座
![运行自定义基座](https://vkceyugu.cdn.bspapp.com/VKCEYUGU-aliyun-xc5d868hqlyo335e89/ac833b40-4658-11eb-8ff1-d5dcf8779628.png)

* 运行示例工程开始体验

## 一、AR-RtmModule

| 函数名                                | 参数                                                         | 说明                                                   |
| ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| setCallBack                           | 无                                                           | 注册sdk事件回调                                        |
| createInstance                        | appId(String)                                                | 创建一个 RtmClient 实例                                |
| login                                 | token(String)、 userId(String)                               | 登录 anyrtc rtm 系统                                          |
| logout                                | 无                                                           | 登出 anyrtc rtm 系统                                   |
| release                               | 无                                                           | 释放当前 RtmClient 实例使用的所有资源                     |
| sendMessageToPeer                     | text(String)、peerId(String)、enableHistoricalMessaging(boolean)、enableOfflineMessaging(boolean) | 向指定用户发送点对点消息或点对点的离线消息。           |
| createChannel                         | channelId(String)                                            | 创建 anyrtc rtm 频道。                                     |
| queryPeersOnlineStatus                | peerIds(Set< String >)                                       | 查询指定用户的在线状态。                               |
| subscribePeersOnlineStatus            | peerIds(Set< String >)                                       | 订阅指定单个或多个用户的在线状态。                     |
| unsubscribePeersOnlineStatus          | peerIds(Set< String >)                                       | 退订指定单个或多个用户的在线状态。                     |
| queryPeersBySubscriptionOption        | option(Integer)                                              | 获取某特定内容被订阅的用户列表。                       |
| setLocalUserAttributes                | 例如：{"age":23,"name":"Jerry"}                               | 全量设置本地用户的属性。                               |
| addOrUpdateLocalUserAttributes        | 同上                                                             | 添加或更新本地用户的属性。                             |
| deleteLocalUserAttributesByKeys       | attributeKeys(List< String >)，例如：{"attributeKeys":["age","name"]}|删除本地用户的指定属性。                               |
| clearLocalUserAttributes              | 无                                                           | 清空本地用户的所有属性。                               |
| getUserAttributes                     | userId(String)                                               | 获取指定用户的全部属性。                               |
| getUserAttributesByKeys               | userId(String)、attributeKeys(List< String >)                | 获取指定用户指定属性名的属性。                         |
| setChannelAttributes                  | channelId(String)、enableNoticeMembers(boolean)、attributes，例如：{"channelId":"909090","enableNoticeMembers":true,"attributes":{"age":23,"name":"Jerry"}} | 全量设置某指定频道的属性                               |
| addOrUpdateChannelAttributes          | 同上                                                              | 添加或更新某指定频道的属性。                           |
| deleteChannelAttributesByKeys         | channelId(String)、attributeKeys(List< String >)、enableNoticeMembers(boolean) | 删除某指定频道的指定属性。                             |
| clearChannelAttributes                   | channelId(String)、enableNoticeMembers(boolean)              | 清空某指定频道的属性。                                 |
| getChannelAttributes                  | channelId(String)                                            | 查询某指定频道的全部属性。                             |
| getChannelAttributesByKeys            | channelId(String)、attributeKeys(List< String >)             | 查询某指定频道指定属性名的属性。                       |
| getChannelMemberCount                 | channelIds(List< String >)                                   | 查询单个或多个频道的成员人数。                         |
| setParameters                         | 无                                                           | 通过 JSON 配置 SDK 提供技术预览或特别定制功能。        |
| setLogFile                            | filePath(String)                                             | 设定日志文件的默认地址。                               |
| setLogFilter                          | filter(int)                                                  | 设置日志输出等级。                                     |
| setLogFileSize                        | fileSizeInKBytes(int)                                        | 设置日志文件大小。                                     |
| join                                  | channelId(String)                                            | 加入频道。                                             |
| leave                                 | channelId(String)                                            | 离开频道。                                             |
| sendChannelMessage                    | channelId(String) 、text(String)、enableHistoricalMessaging(boolean)、enableOfflineMessaging(boolean) | 发送频道消息。                                         |
| getMembers                            | channelId(String)                                           | 获取频道成员列表。                                     |
| channelRelease                        | channelId(String)                                            | 释放该频道的所有资源。                                 |
| setCallEventListener                  | 无                                                              | 设置 RtmCallManager 实例的监听器。                     |
| sendLocalInvitation                   | calleeId(String)、channelId(String)、content(String)          | 发送呼叫邀请给对方。                                   |
| acceptRemoteInvitation                | calleeId(String)、response(String)                           | 接受来自对方的呼叫邀请。                               |
| refuseRemoteInvitation                | calleeId(String)、response(String)                           | 拒绝来自对方的呼叫邀请。                               |
| cancelLocalInvitation                 | calleeId(String)、channelId(String)、content(String)         | 取消给对方的呼叫邀请                                   |

## 二、方法回调

1. login(登录rtm)

{"code": 0}

2. logout(登出rtm)

{"code": 0}

3. queryPeersOnlineStatus(查询指定用户的在线状态)

{"peerOnlineStatus":[{"peerId":"123","state":1}],"code":0}

4. subscribePeersOnlineStatus(订阅指定单个或多个用户的在线状态)

{"code": 0}

5. unsubscribePeersOnlineStatus(订阅指定单个或多个用户的在线状态)

{"code": 0}

6. queryPeersBySubscriptionOption(获取某特定内容被订阅的membersOnSuccess用户列表)

{"peers":["123","456"],@"code":0}

peers为订阅用户id数组

7. setLocalUserAttributes(全量设置本地用户的属性)

{"code": 0}

8. addOrUpdateLocalUserAttributes(添加或更新本地用户的属性)

{"code": 0}

9. deleteLocalUserAttributesByKeys（删除本地用户的指定属性）

{"code": 0}

10. clearLocalUserAttributes（清空本地用户的所有属性）

{"code": 0}

11. getUserAttributes(获取指定用户的全部属性)

{"userAttributesList":{"age":23,"name":"Jerry"},"userId":"123", "code":0}

12. getUserAttributesByKeys(获取指定用户指定属性名的属性)

{"userAttributesList":{"age":23,"name":"Jerry"},"userId":"123", "code":0}

13. setChannelAttributes(全量设置某指定频道的属性)

{"code": 0}

14. addOrUpdateChannelAttributes(添加或更新某指定频道的属性)

{"code": 0}

15. deleteChannelAttributesByKeys(删除某指定频道的指定属性)

{"code": 0}

16. clearChannelAttributes(清空某指定频道的属性)

{"code": 0}

17. getChannelAttributes(查询某指定频道的全部属性)

{"channelAttributes":{"age":23,"name":"Jerry"}, "code":0}

18. getChannelAttributesByKeys(查询某指定频道指定属性名的属性)

{"channelAttributes":{"age":23,"name":"Jerry"}, "code":0}

listDic 例如：{“age":23,"name":"Jerry"} 

19. getChannelMemberCount(查询单个或多个频道的成员人数)

{"memberCounts":[{"channelId":"909090","count”:2}],"code":0}

20. join(加入频道)

{"code": 0}

21. leave(离开频道)

{"code": 0}

22. sendChannelMessage(发送频道消息)

{"code": 0}

23. getMembers(获取频道成员列表)

{"members":[{"channelId":"909090","userId":"123456"}],"code":0}

24. sendLocalInvitation、acceptRemoteInvitation、refuseRemoteInvitation、cancelLocalInvitation

{"code": 0}

## 三、事件回调

### 2.1 RtmClientListener

1. onConnectionStateChanged（ SDK 与 anyRTC rtm系统的连接状态发生改变回调 ）

```
{"rtmEvent":"onConnectionStateChanged","state":0,"reason":0}
```
2. onPeerMessageReceived（  收到点对点消息回调  ）

```
{"rtmEvent":"onPeerMessageReceived","serverReceivedTs":0,"text":"message","OfflineMessage":0,"messageType":0,"peerId":"123"}
```
3. onPeersOnlineStatusChanged（  被订阅用户在线状态改变回调  ）

```
{"rtmEvent":"onPeersOnlineStatusChanged","peersStatus":[{"peerId":"123","state":0}]}
```

### 2.2 RtmChannelListener

​    **1.onAttributesUpdated** （频道属性更新回调）

```
{"rtmEvent":"onAttributesUpdated", "attributeList":[{"key":"name","value":"Jerry","lastUpdateUid":"123","lastUpdateTs":0}]}
```
​    **2.onMemberCountUpdated** （频道成员人数更新回调）

```
{"rtmEvent":"onMemberCountUpdated","memberCount": 0}
```
​    **3.onMemberJoined** （远端用户加入频道回调）

```
{"rtmEvent":"onMemberJoined","userId": "123","channelId": "909090"}
```
​    **4.onMemberLeft** （频道成员离开频道回调）

```
{"rtmEvent":"onMemberLeft","userId": "123","channelId": "909090"}
```
​    **5.onChannelMessageReceived** （收到频道消息回调）

```
{"rtmEvent":"onChannelMessageReceived","type":0,"text":"message","serverReceivedTs":0,"isOfflineMessage":true, "userId": "123","channelId": "909090"}
```

​        

### 2.3 RtmCallEventListener

​    **1.onLocalInvitationAccepted** （返回给主叫：被叫已接受呼叫邀请）

```
{"rtmEvent":"onLocalInvitationAccepted","calleeId": "123","content": "","channelId": "909090","state": 0,"getResponse": "","response": ""}
```
​    **2.onLocalInvitationCanceled** （返回给主叫：呼叫邀请已被取消）

```
{"rtmEvent":"onLocalInvitationCanceled","calleeId":"123","content": "","channelId":"909090","state": 0}
```
​    **3.onLocalInvitationFailure** （返回给主叫：呼叫邀请进程失败）

```
{"rtmEvent":"onLocalInvitationFailure","calleeId": "123","content": "","channelId":"909090","state": 0,"code": 0}
```
​    **4.onLocalInvitationReceivedByPeer** （返回给主叫：被叫已收到呼叫邀请）

```
{"rtmEvent":"onLocalInvitationReceivedByPeer", "calleeId": "123","content": "","channelId": "909090","state":0}
```
​    **5.onLocalInvitationRefused** （返回给主叫：被叫已拒绝呼叫邀请）

```
{"rtmEvent":"onLocalInvitationRefused","calleeId":"123", "content":"","channelId":"909090","state": 0,"getResponse": "","response": ""}
```
​    **6.onRemoteInvitationAccepted** （返回给被叫：接受呼叫邀请成功）

```
{"rtmEvent":"onRemoteInvitationAccepted","callerId":"123","content":"","channelId":"909090","state": 0,"response": ""}
```
​    **7.onRemoteInvitationCanceled** （返回给被叫：主叫已取消呼叫邀请）

```
{"rtmEvent":"onRemoteInvitationCanceled","callerId": "123", "content": "","channelId":"909090","state": 0}
```
​    **8.onRemoteInvitationFailure** （返回给被叫：来自主叫的呼叫邀请进程失败）

```
{"rtmEvent":"onRemoteInvitationFailure","callerId":"123","content":"","channelId":"909090","state":0}
```
​    **9.onRemoteInvitationReceived** （返回给被叫：收到一个呼叫邀请）

```
{"rtmEvent":"onRemoteInvitationReceived","callerId":"123","content":"","channelId":"909090","state": 0}
```
​    **10.onRemoteInvitationRefused** （返回给被叫：拒绝呼叫邀请成功）

```
{"rtmEvent":"onRemoteInvitationRefused","callerId":"123", "content": "","channelId":"909090","state":0,"response": ""}
```

## 四、反馈与建议
- 如多在集成过程中遇到问题，请咨询[anyRTC在线客服(]https://www.anyrtc.io)；
- QQ技术交流群：554714720
- 联系电话:021-65650071-816
- Email:hi@dync.cc





