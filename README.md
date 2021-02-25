# cloud2020
关于尚硅谷SpringCloud2020的学习项目
官网文档传送门：
SpringCloud: https://spring.io/projects/spring-cloud/

这个网址是各springcloud组件的配置介绍，自己搭建组件环境可以考虑看这个。

Seata： https://seata.io/zh-cn/docs/overview/what-is-seata.html

分布式事务解决的框架，文档介绍很详细，推荐。

Nacos： https://nacos.io/zh-cn/docs/what-is-nacos.html

那个替代Eureka和Config的男人。

Sentinel：https://github.com/alibaba/Sentinel/wiki/%E4%BB%8B%E7%BB%8D

在Hystrix基础上增加了流控规则和持久化,alibaba体系的一员。

#### 微服务
1 建modual
2 改pom
3 写yml
4 主启动
5 业务类


#### 5 业务类

1.  建表sql
2.  entities
3.  dao
4.  service
5.  controller
#### 使用说明

1.  微服务提供者8001
2.  客户端消费者80
3.  xxxx

#### 参与贡献
1、Consul
E:\BaiduNetdiskDownload\software\consul_1.7.2_windows_amd64
下面使用cmd启动 consul agent -dev
访问localhost:8500

2.Ribbon : 负载均衡+RestTemplate调用
Ribbon其实就是一个软负载均衡的客户端组件,  他可以和其他所需请求的客户端结合使用,和eureka结合只是其中一个实例.
Ribbon核心组件IRule :IRule:根据特定算法从服务列表中选取一个要访问的服务;
com.netflix.loadbalancer.RoundRobinRule 轮询
com.netflix.loadbalancer.RandomRule 随机
com.netflix.loadbalancer.RetryRule 先按照RoundRobinRule的策略获取服务,如果获取服务失败则在指定时间内进行重试,获取可用的服务
WeightedResponseTimeRule 对RoundRobinRule的扩展,响应速度越快的实例选择权重越多大,越容易被选择
BestAvailableRule 会先过滤掉由于多次访问故障而处于断路器跳闸状态的服务,然后选择一个并发量最小的服务
AvailabilityFilteringRule 先过滤掉故障实例,再选择并发较小的实例
ZoneAvoidanceRule 默认规则,复合判断server所在区域的性能和server的可用性选择服务器
负载均衡算法：
![img.png](img.png)

