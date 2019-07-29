# 我该怎么控制集群用户的权限？

* 团队所有成员通过各自子账号的config文件访问集群
* 通过控制台的"授权管理"来配置每个子账号在集群中的权限

{% hint style="info" %}
主账号的证书无法吊销，为了避免成员离开造成的权限泄露，请务必使用子账号来管理集群，主账号只用来做授权
{% endhint %}

### 参考：

{% embed url="https://help.aliyun.com/document\_detail/87656.html?spm=a2c4g.11174283.6.582.29352ceezqR4My" caption="官方文档" %}

{% embed url="https://yq.aliyun.com/articles/700120?msgid=13897841" %}



