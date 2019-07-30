# 建集群的规划

* 网络规划，有四个网段需要规划，如果做网络打通，不能有冲突
  * vpc网段
  * vswitch网段
  * pod网段
  * service网段
* 网络模型：
  * 插件：优选terway，除非明确不需要network policy特性
  * kube-proxy代理模式：推荐IPvs，在集群规模大时性能更好
* 机器配置：
  * master节点建议用SSD盘，因为etcd对io性能要求高
  * worker节点建议加一块数据盘，初始化过程中会自动把这块盘mount到docker和kubelet目录
* 相关服务：
  * 云监控，建议打开，免费
  * 日志服务，建议打开，按量付费
* 组件：
  * ingress，建议安装
  * AGS，工作流引擎，按需安装

{% embed url="https://help.aliyun.com/document\_detail/98886.html?spm=a2c4g.11186623.6.778.4d1f1c9b4RlB61" %}



