---
title: "Set Resource Limits in Kubernetes Pods"
seoTitle: "Kubernetes Pod Resource Limiting Guide"
seoDescription: "Learn how to set memory and CPU resource limits for Kubernetes pods with a step-by-step guide"
datePublished: Mon Oct 14 2024 09:28:15 GMT+0000 (Coordinated Universal Time)
cuid: cm28tachk000m0al9drhe4n4x
slug: set-resource-limits-in-kubernetes-pods
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728896872813/1f395ec8-ce53-471b-b629-6badce23620e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728898075508/feb661ce-29cc-45a6-b50d-3f880b6e5d05.png
tags: kubernetes, developer, devops, k8s, devops-articles

---

### Steps

* Create a pod named `httpd-pod` with a container named `httpd-container`.
    
* Use the `httpd` image with the `latest` tag (`httpd:latest`).
    
* Set resource requests:
    
    * Memory: `15Mi`
        
    * CPU: `100m`
        
* Set resource limits:
    
    * Memory: `20Mi`
        
    * CPU: `100m`
        

### Tasks

1. Create a manifest yaml file, `httpd-pod.yaml`
    
    ```yaml
    apiVersion: v1
    kind: Pod
    metadata:
      name: httpd-pod
    spec:
      containers:
      - name: httpd-container
        image: httpd:latest
        resources:
          requests:
            memory: "15Mi"
            cpu: "100m"
          limits:
            memory: "20Mi"
            cpu: "100m"
    ```
    
    As I prefer **EOF**,
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728897681682/4e7e5444-0be3-41cb-8588-f306fb9da848.png align="left")
    
2. Apply the manifest file
    
    ```bash
    kubectl apply -f httpd-pod.yaml
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728897772682/f5bb62f3-32ca-49ff-ae60-239252207c1a.png align="center")
    
3. `pod/httpd-pod` created. Now, Verify the Pod.
    
    ```bash
    kubectl get pods
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728897866907/7a434ef0-23c0-4b2e-8baf-7be00ccf8513.png align="left")
    
4. Then, check the resources on given pod
    
    ```bash
    kubectl describe pod httpd-pod
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728897990933/e2bc4c6c-5adf-4529-8dc8-6a5cf42645c7.png align="center")
    

#k8s #kubernetes #devops #pods #limitation #happylearning