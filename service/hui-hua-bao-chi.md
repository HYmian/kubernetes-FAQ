# 如何做会话保持？

ACK做会话保持需要在三个层面上完成

* 负载均衡（SLB）

{% embed url="https://help.aliyun.com/video\_detail/91941.html?spm=5176.11065259.1996646101.searchclickresult.225d22e90f5ivB" caption="配置视频" %}

{% embed url="https://help.aliyun.com/knowledge\_detail/55202.html?spm=5176.11065259.1996646101.searchclickresult.4d3f22e9vhaaHZ" caption="配置说明" %}

* ingress controller（optional）

{% embed url="https://kubernetes.github.io/ingress-nginx/examples/affinity/cookie/" caption="NGINX ingress controller annotation" %}

* service

In any of these proxy model, any traffic bound for the Service’s IP:Port is proxied to an appropriate backend without the clients knowing anything about Kubernetes or Services or Pods. Client-IP based session affinity can be selected by setting `service.spec.sessionAffinity` to “ClientIP” \(the default is “None”\), and you can set the max session sticky time by setting the field `service.spec.sessionAffinityConfig.clientIP.timeoutSeconds` if you have already set `service.spec.sessionAffinity` to “ClientIP” \(the default is “10800”\).

{% embed url="https://kubernetes.io/docs/concepts/services-networking/service" caption="service spec" %}



