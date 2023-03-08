<details>
<summary>COMMON</summary>

  > See kubectl version
  ```
  kubectl version --output=yaml
  ```
  > Get all contexts
  ```
  kubectl config get-contexts
  ```
  > Get current context
  ```
  kubectl config current-context
  ```
  > Switch context (for example, to use 'docker-desktop' context)
  ```
  kubectl config use-context docker-desktop
  ```

</details>

<details>
<summary>a1_POD</summary>

  > Get pods
  ```
  kubectl get pod
  ```
  > Create pod (from 'a1_pod.yaml' file)
  ```
  kubectl apply -f ~/code-doc-book/k8s/a1_pod.yaml 
  ```
  > or
  ```
  kubectl create -f ~/code-doc-book/k8s/a1_pod.yaml
  ```
  > Get a describe of pod named 'my-pod'
  ```
  kubectl describe pod my-pod
  ```
  > Clean up all the cluster
  ```
  kubectl delete pod --all
  ```

</details>
