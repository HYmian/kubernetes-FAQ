# 怎么防止mountPath内的文件被清除？

我们经常会遇到把configmap/secret mount进pod作为配置文件的场景

默认情况下，volumeMounts指定的路径下的原有文件会被清除，里面只剩下configmap/secret的内容

这时候，如果我们想要挂载configmap/secret里的内容成一个单独的文件，就需要使用subpath的概念，参考下面的例子：

{% embed url="https://github.com/HYmian/kubernetes-samples/tree/master/volume" %}

{% hint style="info" %}
注意：subPath的值必须和mountPath最后一段的路径相同
{% endhint %}

subPath的介绍参考这里：

{% embed url="https://kubernetes.io/docs/concepts/storage/volumes/\#using-subpath" %}



