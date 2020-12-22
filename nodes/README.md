1. Get the name of all the nodes and their taint effect if any. <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get nodes -o jsonpath='{range $.items[*]} {.metadata.name} {.spec.taints[*].effect}{"\n"}{end}'
```

**Output**

```shell
kubemaster NoSchedule
kubenode01
kubenode02
```

</details>

2. Get the name of the all the nodes and their corresponding InternalIP address. <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get nodes -o jsonpath='{range .items[*]}{.metadata.name}{"\t"}{.status.addresses[?(@.type=="InternalIP")].address}{"\n"}{end}'
```

**Output**

```shell
kubemaster      192.168.56.2
kubenode01      192.168.56.3
kubenode02      192.168.56.4
```

</details>
