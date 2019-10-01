# memo

以下のコマンドで、Nginx のイメージを使用した Pods の雛形ができる。

```
kubectl run pod-name --image=nginx --restart=Never --dry-run -o yaml > pod.yaml
```

```
# pod.yaml


apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: pod-name
  name: pod-name
spec:
  containers:
  - image: nginx
    name: pod-name
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Never
status: {}

```
