# 动脑实验---ROS2中的实时协作问题研究
## 问题叙述
相比于ROS1，ROS2对实时应用给予了更大的关注。研究在ROS的实时应用场景中如何有效处理多个组件的协调和同步。

## ROS2的基本机制
由多个节点组成的ROS Graph来同时处理数据，每一个节点负责控制一个部件同时每一个节点都可以收发数据到其他节点，然后节点通过激活callback来处理每一个传入的信息。
![](https://github.com/babohhauru/Concurrency-System/blob/main/Report/Nodes-TopicandService.gif)[1]

节点之间的通信方式主要分为了Topic(Publisher-Subscriber), Services(Call-And-Response)和Action(Client-Server)三种。其中Topic是最常见的，Topic充当节点之间交换消息的总线。每一个节点都可以向多个Topic发送数据也同时可以Subscribe多个Topic。

## ROS2实时计算
![Figure.2 [1]](https://github.com/babohhauru/Concurrency-System/blob/main/Report/rosapp.png)


由于通信中产生的延迟，ROS在升级到ROS2的过程中使用了DDS(Data Distribution Service)来作为传输系统以及使用QoS(Quality of Service)，并且ROS2中引入了Excutor来支持执行并管理以此确保实时性能。
    















[1]Charles Randolph, Improving the Predictability of Event Chains in ROS2, TU Delft