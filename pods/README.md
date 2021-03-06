1. Get the IP of the pods with label app=nginx. <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get pods -l app=nginx -o jsonpath='{range .items[*]}{.status.podIP}{"\n"}{end}'
```

**Output**

```shell
10.38.0.2
10.32.0.3
10.32.0.4
10.38.0.1
```

</details>

2. Get all the pods that are on specific node. Change the node name according to your requirement in `@.spec.nodeName=="kubenode01"` <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get pods -o jsonpath='{range $.items[?(@.spec.nodeName=="kubenode01")]}{.metadata.name}{"\t"}{.spec.nodeName}{"\n"}{end}'
```

**Output**

```shell
nginx-6799fc88d8-78mwd  kubenode01
nginx-6799fc88d8-c7cpb  kubenode01
test-iptables-cb64cc545-dn9t8   kubenode01
```

</details>

3. Get all the pods that are using specific configmap. Change the configmap name according to your requirement in `@.spec.volumes[*].configMap.name=="test-config"` <br/>**K8s** version used - **v1.19.2**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get pods -o jsonpath='{range .items[?(@.spec.volumes[*].configMap.name=="test-config")]}{.metadata.name}{"\t"}{.spec.volumes[*].configMap.name}{"\n"}{end}'
```

**Output**

```shell
test-pod-cm     test-config
```

</details>

4. Get all the pods that are using specific persistent volume claim. Change the pvc name according to your requirement in `@.spec.volumes[*].persistentVolumeClaim.claimName=="test-pvc"` <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get pods -o jsonpath='{range .items[?(@.spec.volumes[*].persistentVolumeClaim.claimName=="test-pvc")]}{.metadata.name}{"\t"}{"\n"}{end}'
```

**Output**

```shell
test-pod-pvc
```

</details>
