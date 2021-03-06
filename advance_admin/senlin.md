# 云主机自动伸缩

自动伸缩（Auto Scaling）可以根据业务需求和伸缩策略，自动调整计算资源。可以通过策略和监控自动地增加或减少集群中的节点数量。在高峰时增加节点，以保证业务和性能不受影响；当需求降低时，自动减少节点数量，以节省资源和降低成本。

典型的使用方法是先创建启动配置，然后根据启动配置创建节点或者集群。创建并给集群附加策略和接收器，通过ceilomerter创建监控项，当有告警时自动调用与集群关联的接收器实现伸缩操作。

## 名词解释

|名称|含义|
|-|-|
|Profile|启动配置文件(文件中定义了实例启动的所有相关参数)|
|Policy|策略(策略与集群配合使用，将策略添加到集群，相应的策略根据策略内容完成集群的改变，产品中使用的策略有负载均衡,伸缩策略,删除策略,健康检测策略)|
|Node|节点(当创建一个 Node 时，nova 会对应创建一个 instance 实例,节点可以加入集群，也可以独立存在)|
|Cluster|伸缩组或集群(集群概念，可在集群上添加启动配置与各种策略)|
|Receiver|接收器(对外提供一个 url 地址， 执行 Post url 地址能够改变集群中的节点数)|
