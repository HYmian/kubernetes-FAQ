# 日志管理

### 开启日志服务

* 创建集群时可以勾选'使用日志服务'
* 如果创建集群时没有打开这个功能，可以手动安装组件

{% embed url="https://help.aliyun.com/document\_detail/87540.html?spm=a2c4g.11174283.6.678.9a722ceeIR8o7S\#h2-url-3" caption="官方文档，包含应用日志如何归档到日志服务" %}

* 部署eventer组件，将K8s的event归档到日志服务中

{% embed url="https://yq.aliyun.com/articles/653451?spm=a2c4e.11153940.blogcont656266.14.75146c9drTAWUS" %}

* 部署npd，将node上的内核错误上报成K8s的event

{% embed url="https://yq.aliyun.com/articles/649863?spm=a2c4e.11153940.blogcont656266.12.75146c9drTAWUS" %}

### 日志功能

* 自动归档K8s审计日志，如delete pod、exec等
* 部署eventer后，可以归档所有的K8s event
* 部署npd后，结合eventer，可以归档所有的node内核错误
* 可以针对所有的记录产生告警

### FAQ

* 如何优化日志服务的费用？

{% embed url="https://help.aliyun.com/document\_detail/103024.html" %}



