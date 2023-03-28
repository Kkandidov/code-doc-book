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
  > View contexts
  
 ```
 kubectl config view
 ```
</details>

---

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

<details>
<summary>a3_DEPLOYMENT</summary>
  
  > Create deployment
  ```
  kubectl apply -f a3_deployment.yaml
  ```
  
  > Check list of pods
  ```
  kubectl get pod
  ```
  
  > Check lis of replicasets
  ```
  kubectl get replicaset
  ```
  
  > Update image version for a container from deployment (set nginx:1.13)
  ```
  kubectl set image deployment my-deployment nginx=nginx:1.13
  ```
  
  > Check list of pods
  ```
  kubectl get pod
  ```
  
  > Check if our pod has a new image (our new pod is my-deployment-f69d497d9-c4jxk)
  ```
  kubectl describe pod my-deployment-f69d497d9-c4jxk
  ```
  
  > Check replicasets
  ```
  kubectl get replicaset
  ```
  
  > Clean up a cluster
  ```
  kubectl delete deployment --all
  ```
</details>

<details>
<summary>a4_RESOURCES</summary>
  
  > Create deployment with resources
  ```
  kubectl apply -f a4_resources.yaml
  ```
  
  > Check pods
  ```
  kubectl get pod
  ```
  
  > Increase resources for deployment
  ```
  kubectl patch deployment my-deployment --patch '{"spec":{"template":{"spec":{"containers":[{"name":"nginx","resources":{"requests":{"cpu":"10"},"limits":{"cpu":"10"}}}]}}}}'
  ```
  
  > Check pods
  ```
  kubectl get pod
  ```
  
  > Check pod with PENDING status (its name is my-deployment-7f9cd6cb65-m7f87)
  ```
  kubectl describe po my-deployment-7f9cd6cb65-m7f87
  ```
  
  > and see the following:
  > Warning  FailedScheduling  108s  default-scheduler  0/1 nodes are available: 1 Insufficient cpu. preemption: 0/1 nodes are available: 1 No preemption victims found for incoming pod.
  
  > clean up cluster
  ```
  kubectl delete deployment --all
  ```
</details>

---

<details>
<summary>B1_DEPLOYMENT_WITH_ENV</summary>
  
  > Apply manifest for creating of a deployment
  ```
  kubectl apply -f b1_deployment_with_env.yaml 
  ```
  
  > Show all the pods
  ```
  kubectl get pod 
  ```
  
  > Check result (fill out your pod name, in this case it is 'my-deployment-57764d7b57-2wbxw')
  ```
  kubectl describe pod my-deployment-57764d7b57-2wbxw
  ```
  
</details>  

<details>
<summary>B2_B3_DEPLOYMENT_WITH_ENV_AND_CONFIGMAP</summary>
  
  > Create config map and apply configma to our deployment
  ```
  kubectl apply -f b2_configmap.yaml
  kubectl apply -f b3_deployment_with_env_and_cm.yaml
  ```
  
  > Get pods
  ```
  kubectl get pod 
  ```
  
  > Check result (in this case pod name is 'my-deployment-57764d7b57-2wbxw')
  ```
  kubectl exec -it my-deployment-57764d7b57-2wbxw -- env
  ```
</details>  

<details>
<summary>B4_B5_DEPLOYMENT_WITH_SECRET</summary>
  
  > Create secret 'test'
  ```
  kubectl create secret generic test --from-literal=test1=asdf --from-literal=dbpassword=1q2w3e
  ```
  
  > Get all the secrets
  ```
  kubectl get secret
  ```
  
  > Get described 'test' secret
  ```
  kubectl get secret test -o yaml
  ```
  
  > Create deployment with secret
  ```
  kubectl apply -f b5_deployment_with_secret.yaml
  ```
  
  > Describe deployment (the name of deployment is 'my-deployment-6fc85868dd-67g2z')
  ```
  kubectl describe pod my-deployment-6fc85868dd-67g2z
  ```
  
  > or once may to enter inside of pod (the name of deployment is 'my-deployment-6fc85868dd-67g2z')
  ```
  kubectl exec -it my-deployment-6fc85868dd-67g2z -- env
  ```
  
  > Apply a manifest with a secret
  ```
  kubectl apply -f b4_secret.yaml
  ```
  
  > Check our secret
  ```
  kubectl get secret test -o yaml
  ```
  
  > Make chenges in our secret (change key name 'test' to 'test1')
  ```
  vim b4_secret.yaml
  ```
  
  > Apply above secret
  ```
  kubectl apply -f b5_deployment_with_secret.yaml
  ```
  
  > Check our secret
  ```
  kubectl get secret test -o yaml
  ```
</details>  

<details>
<summary>B6_B7_DEPLOYMENT_WITH_CONFIGMAP</summary>
  
  > Create configmap
  ```
  kubectl apply -f b6_configmap.yaml     
  ```
  
  > Create deployment
  ```
  kubectl apply -f b7_deployment_with_configmap.yaml
  ```
  
  > Enter inside of a container (container name is my-deployment-5f7c7cbcd8-99cx4)
  ```
  kubectl exec -it my-deployment-5f7c7cbcd8-99cx4 -- bash
  ```
  
  > Do port forwarding
  ```
  kubectl port-forward my-deployment-5f7c7cbcd8-99cx4 8080:80 &
  ```
  
  > Check result
  ```
  curl 127.0.0.1:8080
  ```
</details>  


<details>
<summary>B8_DEPLOYMENT_WITH_DOWNWARD</summary>
  
  > Apply deployment
  ```
  kubectl apply -f b8_deployment_with_downward_api.yaml   
  ```
  
  > Check env
  ```
  kubectl exec -it my-deployment-59c5846cbb-9bn6k -- env 
  ```
  
  > Clean up everything
  ```
  kubectl delete deployment my-deployment
  kubectl delete configmap my-configmap-env
  kubectl delete configmap my-configmap
  kubectl delete secret test
  ```
</details>  
