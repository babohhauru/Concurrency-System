# ROS2中的实时协作问题研究
## 问题叙述
相比于ROS1，ROS2对实时应用给予了更大的关注。研究在ROS的实时应用场景中如何有效处理多个组件的协调和同步。

## ROS2的基本机制
由多个节点组成ROS graph来同时处理数据，每一个节点负责控制一个部件同时每一个节点都可以收发数据到其他节点。
![](c:%5CUsers%5Cbabo%5CDesktop%5CNodes-TopicandService.gif)
节点之间的通信方式主要分为了Topic(Publisher-Subscriber模型), Services(Call-And-Response模型)和Action(Client-Server)三种。其中Topic是最常见的，Topic充当节点之间交换消息的总线每一个节点都可以向任意数量的Topic发送数据，同时Subscribe任意个Topic。