---
title: "Deploy Replica Set in Kubernetes Cluster"
seoTitle: "Kubernetes Replica Set Deployment Guide"
seoDescription: "Learn how to deploy and manage a ReplicaSet in a Kubernetes cluster using Nginx. Complete guide with step-by-step instructions"
datePublished: Mon Oct 14 2024 11:00:40 GMT+0000 (Coordinated Universal Time)
cuid: cm28wl702000v09laaopqa8za
slug: deploy-replica-set-in-kubernetes-cluster
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728902588050/cfcdcf65-e16d-4d31-a2a8-1a994f95f678.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728903621775/16282ff8-7cdd-4264-bf47-fc75acd92293.png
tags: kubernetes, devops, k8s, devops-articles, deploymentmanagement-replicaset-rollingupdates-rollback-kubernetes-scaling-deploymenterrors-applicationconfiguration-resourcemanagement-imagepullerror-insufficientpermission-limitranges-quota

---

### Tasks

* Create a ReplicaSet using the `nginx` image with the `latest` tag (specify as `nginx:latest`) and name it `nginx-replicaset`.
    
* Apply labels: `app` as `nginx_app`, `type` as `front-end`.
    
* Name the container `nginx-container`. Ensure the replica count is `4`.
    

### Steps

1. Create a manifest file name it as `replicaset.yaml`.
    
    ```yaml
    apiVersion: apps/v1
    kind: ReplicaSet
    metadata:
      name: nginx-replicaset
    spec:
      replicas: 4
      selector:
        matchLabels:
          app: nginx_app
          type: front-end
      template:
        metadata:
          labels:
            app: nginx_app
            type: front-end
        spec:
          containers:
          - name: nginx-container
            image: nginx:latest
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728902865718/be6427ce-13de-4ccb-ae28-a81ed1f40e19.png align="left")
    
2. Now apply the configuration in k8s cluster.
    
    ```bash
    kubectl apply -f replicaset.yaml
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728903188734/84dfaeeb-4785-4782-a622-3064d9fb2e1c.png align="left")
    
3. Get replicaset
    
    ```bash
    kubectl get replicaset
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728903449404/349deb87-eb3d-4a38-87cc-4dd8f93455b7.png align="left")
    
4. Check the description of this replicaset.
    
    ```bash
    kubectl describe replicaset nginx-replicaset
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728903546393/73cfded7-cf0d-419c-b849-7c9e5eebff82.png align="center")
    
    #k8s #kubernetes #replicaset