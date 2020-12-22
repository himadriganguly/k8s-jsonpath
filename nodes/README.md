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

3. Get the name of the all the nodes' name, os image, os architecture, pod cidrs, internal and external ip address. <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get nodes -o custom-columns='NODE-NAME:.metadata.name,OS-IMAGE:.status.nodeInfo.osImage,OS-ARCH:.status.nodeInfo.architecture,POD-CIDRs:.spec.podCIDRs[*],INTERNAL-IP:.status.addresses[?(@.type=="InternalIP")].address,EXTERNAL-IP:.status.addresses[?(@.type=="ExternalIP")].address'
```

**Output**

```shell
NODE-NAME    OS-IMAGE             OS-ARCH   POD-CIDRs       INTERNAL-IP    EXTERNAL-IP
kubemaster   Ubuntu 16.04.7 LTS   amd64     10.244.0.0/24   192.168.56.2   <none>
kubenode01   Ubuntu 16.04.7 LTS   amd64     10.244.1.0/24   192.168.56.3   <none>
kubenode02   Ubuntu 16.04.7 LTS   amd64     10.244.2.0/24   192.168.56.4   <none>
```

</details>
