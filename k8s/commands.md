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

<details>
<summary>a2_REPLICASET</summary>

  > Create replicaset
  ```
  kubectl create -f a2_replicaset.yaml
  ```
  
  > or
  ```
  kubectl apply -f a2_replicaset.yaml
  ```

  > Get pods
  ```
  kubectl get pod
  ```
  
  > Scale replicaset
  ```
  kubectl scale replicaset my-replicaset --replicas 3
  ```
  
  > Get pods
  ```
  kubectl get pod
  ```
  
  > Delete pod (for example my-replicaset-pbtdm)
  ```
  kubectl delete pod my-replicaset-pbtdm
  ```
  
  > Get pods
  ```
  kubectl get pod
  ```
  
  > update replicaset template (image is getting nginx=nginx:1.13)
  ```
  kubectl set image replicaset my-replicaset nginx=nginx:1.13
  ```
  
  > Get description of replicaset
  ```
  kubectl describe replicaset my-replicaset
  ```
  
  > Get description of pod (for example my-replicaset-j746n pod)
  ```
  kubectl describe pod my-replicaset-j746n 
  ```
  
  > Delete pod (for example my-replicaset-j746n pod)
  ```
  kubectl delete pod my-replicaset-j746n
  ```
  
  > Get description of new pod (my-replicaset-rf999 pod)
  ```
  kubectl describe pod my-replicaset-rf999
  ```
  
  > clean up cluster
  ```
  kubectl delete replicaset --all
  ```
</details>
