---
title: "Revert Deployment to Previous Version in Kubernetes"
seoTitle: "Revert Deployment to Previous Version"
seoDescription: "Learn how to rollback your Kubernetes deployment to a previous version with these simple steps and ensure stability in your environment"
datePublished: Mon Oct 14 2024 10:39:07 GMT+0000 (Coordinated Universal Time)
cuid: cm28vthhe000109krcoeb8td6
slug: revert-deployment-to-previous-version-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728901692959/8bf54529-28d2-44f3-8014-e3bff006fe50.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728902331852/c8da3835-107d-4961-8f31-75a62eca70d7.png
tags: kubernetes, devops, k8s, devops-articles

---

### Tasks

* Rollback the deployment named `nginx-deployment` to the previous revision.
    

### Steps

1. Check the existing deployments
    
    ```bash
    kubectl get deployments
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728901797671/5bb60131-082c-4bec-b7b3-531180ffb64b.png align="left")
    
2. Roll Back the Deployment
    
    ```bash
    kubectl rollout undo deployment/nginx-deployment
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728901930974/8ac10e8b-9487-41de-acdd-063252c649c5.png align="center")
    
3. Now verfify with status
    
    ```bash
    kubectl rollout status deployment/nginx-deployment
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728901996974/7e414b18-2e54-44b2-915a-bd9a3892037d.png align="center")
    
4. List pods
    
    ```bash
    kubectl get pods
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728902071340/521e8fd1-d4f3-49b8-ae14-9ad1047e81ba.png align="center")
    
5. Confirm the image version
    
    ```bash
    kubectl describe deployment nginx-deployment
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728902162171/729528e1-cc80-44ce-8af0-d6fb376c5807.png align="center")
    
    You can see image version is `nginx:1.16` now.
    
6. Out of the box, chill method with `404 error`;
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728902288827/d9a51ac9-52b1-4801-9766-65f982265442.png align="center")
    
    #k8s #revert #happylearning