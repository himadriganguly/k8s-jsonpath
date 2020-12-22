1. Get the IP of the pods with label app=nginx. <br/>K8s version used - **v1.19.0**

<details>
  <summary>Click to expand!</summary>

`kubectl get pods -l app=nginx -o jsonpath='{range .items[*]}{.status.podIP}{"\n"}{end}'`

</details>
