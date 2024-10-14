---
title: "Setup Kubernetes Namespaces and PODs"
seoTitle: "Kubernetes: Setup Namespaces and PODs"
seoDescription: "Learn how to set up Kubernetes namespaces and deploy PODs using NGINX with step-by-step instructions"
datePublished: Mon Oct 14 2024 09:02:22 GMT+0000 (Coordinated Universal Time)
cuid: cm28sd1ur000209jw7pkkesaf
slug: setup-kubernetes-namespaces-and-pods
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728895051410/ff7bd2c8-4942-461d-992c-3ce2f8626e94.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728896528494/c3a8f377-6a38-4494-adff-5d7c16ee1cbd.png
tags: kubernetes, devops, k8s, devops-articles, namespaces, pods

---

### Tasks

* Create a namespace named `dev`.
    
* Deploy a pod named `dev-nginx-pod` in the `dev` namespace.
    
* Use the `nginx` image with the `latest` tag for the pod.
    
* Ensure to specify the image tag as `nginx:latest`.
    

### Tasks

1. First create the namespace named dev.
    
    ```bash
    kubectl create namespace dev
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728895411813/bd19b64e-8123-4201-8b0f-c05bb12354be.png align="left")
    
2. Manifest with `yaml file`:
    
    ```yaml
    apiversion: v1
    kind: Namespace
    metadata:
      name: dev
    ```
    
    But I prefer using EOF
    
    ```bash
    cat <<EOF > namespace-dev.yaml
    apiVersion: v1
    kind: Namespace
    metadata:
      name: dev
    EOF
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728895874115/be9cf035-2963-4559-b3f3-151621049c93.png align="left")
    
3. Create namespace now:
    
    ```bash
    kubectl create -f namespace-dev.yaml --save-config
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728895998189/e69a4180-d44b-404a-8d99-fa0ccb68e4b5.png align="center")
    
4. Create pods now, `nginx-pod.yaml`
    
    ```yaml
    apiVersion: v1
    kind: Pod
    metadata:
      name: dev-nginx-pod
      namespace: dev
    spec:
      containers:
      - name: nginx
        image: nginx:latest
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728896179907/dcdf3d8a-e5d7-4e96-af0e-4169d9732742.png align="left")
    
5. Apply the YAML manifest file.
    
    ```yaml
    kubectl apply -f nginx-pod.yaml
    ```
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728896229529/9315abe4-807d-46ed-a73c-3363a5ca9951.png align="center")
    
    Now List Namespaces
    
    ```yaml
    kubectl get namespaces
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728896319761/5c3308e9-7728-4347-bfa8-366c9bcc4e0d.png align="left")
    
7. List Pods in a Namespace
    
    ```bash
    kubectl get pods -n dev
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728896411670/36a3a149-71b4-4f46-a27a-c019c6e8b38a.png align="center")
    
    #k8s #kubernetes #pods #namespace #happylearning :)