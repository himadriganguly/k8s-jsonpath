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
