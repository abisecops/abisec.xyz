---
title: "Schedule Cronjobs in Kubernetes"
seoTitle: "Kubernetes Cronjob Scheduling Guide"
seoDescription: "Learn how to schedule cronjobs in Kubernetes using httpd image, yaml manifests, and kubectl for efficient task automation"
datePublished: Tue Oct 15 2024 17:46:08 GMT+0000 (Coordinated Universal Time)
cuid: cm2aqigzo00010akw39vi02jk
slug: schedule-cronjobs-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729013210536/d775c58b-d758-47b6-b179-f2b2a23da527.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1729014303190/3107762c-c5dd-4f15-8bd2-93279bfad144.png
tags: kubernetes, developer, devops, k8s, cronjob, devops-articles

---

### Tasks

* Create a cronjob named `xfusion`.
    
* Set its schedule to something like `*/7 * * * *`. You can set any schedule for now.
    
* Name the container `cron-xfusion`.
    
* Utilize the `httpd` image with `latest tag` (specify as `httpd:latest`).
    
* Execute the dummy command `echo Welcome to xfusioncorp!`.
    
* Ensure the restart policy is `OnFailure`.
    

### Steps

1. Create a manifest file `cronjob.yaml` using given details.
    
    ```yaml
    apiVersion: batch/v1
    kind: CronJob
    metadata:
      name: xfusion
    spec:
      schedule: "*/7 * * * *"
      jobTemplate:
        spec:
          template:
            spec:
              restartPolicy: OnFailure
              containers:
                - name: cron-xfusion
                  image: httpd:latest
                  command: ["echo", "Welcome to xfusioncorp!"]
    ```
    
    ```bash
    cat <<EOF>cronjob.yaml
    apiVersion: batch/v1
    kind: CronJob
    metadata:
      name: xfusion
    spec:
      schedule: "*/7 * * * *"
      jobTemplate:
        spec:
          template:
            spec:
              restartPolicy: OnFailure
              containers:
                - name: cron-xfusion
                  image: httpd:latest
                  command: ["echo", "Welcome to xfusioncorp!"]
    EOF
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729013879975/7209f03b-bf38-406b-99e1-adc23f91cba8.png align="left")
    
2. Now apply the yaml manifest file.
    
    ```bash
    k apply -f cronjob.yaml
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729013949582/a5a2b526-d01a-4e14-b9ff-5db6a63d29e4.png align="center")
    
    * We can also use `kubectl apply -f cronjob.yaml` too.
        
3. Let’s get the result.
    
    ```bash
     k get cronjob -o wide
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729014098343/38b4bfa6-abb5-46bb-8f59-08c496b9dd3a.png align="left")
    
4. Describe the cronjob now.
    
    ```bash
    k describe cronjob
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729014220136/4452faa6-180d-439d-bbdb-ce420136442a.png align="center")
    
    #cronjob #k8s #kubernetes #happylearning