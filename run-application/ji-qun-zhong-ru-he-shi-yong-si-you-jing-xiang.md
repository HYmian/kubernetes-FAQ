# 集群中如何使用私有镜像？

如果你之前使用过docker，肯定知道docker使用私有镜像时，要先在主机上做login，类似下面的命令

```bash
docker login [my registry]
```

但是如果你现在要用kubernetes来管理几十个节点，甚至成百上千的节点时，我们要一台台的在主机上做docker login就太麻烦了

### 那我用ansible来做批量docker login可以吗？

当然可以，这样做显然是比你手动去依次操作要好，省去了繁复的操作，但是仍然有不尽如人意的地方，那就是主机上做docker login后，登录这台主机上的人可以任意使用这个私有仓库里的镜像了，这一定不是你想看到的局面

即使你对主机做了非常严格的管控，还有一种情况是不能避免的，所有调度到主机上的pod都可以随意的使用已经登录的私有仓库的镜像，所以我们还是老老实实的使用地道的K8s官方推荐的方式来使用私有镜像吧

{% embed url="https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/\#create-a-pod-that-uses-your-secret" %}

{% code-tabs %}
{% code-tabs-item title="pod\_with\_image\_pull\_secrets.yaml" %}
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: private-reg
spec:
  containers:
  - name: private-reg-container
    image: <your-private-image>
  imagePullSecrets:
  - name: regcred
```
{% endcode-tabs-item %}
{% endcode-tabs %}





