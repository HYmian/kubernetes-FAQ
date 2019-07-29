# 怎么控制应用之间的亲和与反亲和？

我们都知道，通过nodeSelector属性，我们可以非常方便的约束pod的调度范围，但是这种调度的规则毕竟简单了点，在很多场景下，我们需要更灵活的调度规则，比如：某一个应用的实例需要分散在不同的节点上，甚至为了更高的可用性，我们可能要求实例分布在不同的可用区内

下面是一个最常见的例子，让同一个应用下的不同实例调度在不同的节点上：

{% embed url="https://github.com/HYmian/kubernetes-samples/blob/master/scheduler/anti\_affinity.yaml" %}

这里我们可以通过不同的**`topologyKey`**来达到不同的调度效果，内置的key：

{% embed url="https://kubernetes.io/docs/concepts/configuration/assign-pod-node/\#built-in-node-labels" caption="built-in node labels" %}

更复杂的亲和性规则参考：

{% embed url="https://kubernetes.io/docs/concepts/configuration/assign-pod-node/\#inter-pod-affinity-and-anti-affinity" %}







