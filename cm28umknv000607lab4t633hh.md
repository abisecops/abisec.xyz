---
title: "Execute Rolling Updates in Kubernetes"
seoTitle: "Kubernetes Rolling Updates Guide"
seoDescription: "Learn how to perform rolling updates on Kubernetes deployments using `nginx:1.17`, ensuring all pods are operational afterward"
datePublished: Mon Oct 14 2024 10:05:45 GMT+0000 (Coordinated Universal Time)
cuid: cm28umknv000607lab4t633hh
slug: execute-rolling-updates-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728899012860/0163ab98-11c0-4bbe-89a3-29803e762543.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728900333130/854a8171-cfdc-4ed9-937b-98315fd6c406.png
tags: nginx, kubernetes, devops, k8s, devops-articles

---

### Tasks

* Execute a rolling update for the application using the `nginx:1.17` image.
    
* Ensure the deployment is named `nginx-deployment`.
    
* Verify that all pods are operational after the update.
    

### Steps

1. Get the description of deployment named `nginx-deployement`
    
    ```bash
    kubectl describe deployment nginx-deployment
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728899602075/47b772d1-adb1-4d8e-92f0-3dd8f4e523a7.png align="center")
    
    We can see there is image: `nginx:1.16`
    
2. Lets update nginx container
    
    ```bash
    kubectl set image deployment/nginx-deployment nginx-container=nginx:1.17
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728899762673/6f5fab4f-60e3-40cf-90a5-d9e964df445f.png align="center")
    
3. Check the Rollout Status.
    
    ```bash
    kubectl rollout status deployment/nginx-deployment
    ```
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728899934460/231dbf92-9947-4703-9d2c-0d1d8250af94.png align="center")
    
5. Again check the update
    
    ```bash
    kubectl describe deployment nginx-deployment
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728899833776/62e95dc1-0350-41e3-aac5-85915db1a501.png align="center")
    
    We can see we have image, `nginx:1.17` now.
    
6. Out of the box.
    
    * Check our nginx is running on web or not.
        
    * ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728900237024/9f5c6802-aab0-4665-ba94-d565c025be21.png align="center")
        
        Not check the nginx version `making 404 error` :p
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728900262970/3f5cbc3b-310c-40e1-a350-63200401533b.png align="center")
        
        #nginx #k8s #kubernetes #happylearning