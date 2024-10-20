---
title: "Set Up Time Check Pod in Kubernetes"
seoTitle: "Kubernetes Time Check Pod Setup Guide"
seoDescription: "Learn how to set up a Kubernetes pod with time-checking functionality using ConfigMap and volume mounts"
datePublished: Sun Oct 20 2024 15:06:39 GMT+0000 (Coordinated Universal Time)
cuid: cm2hq0n9t000109ib0ewxgvrh
slug: set-up-time-check-pod-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729179915591/f16fc29e-74d2-4bdc-bea4-e56b67e77d25.png
tags: cloud, kubernetes, cloud-computing, devops, k8s

---

### Tasks

* Create a pod called `time-check` in the `devops` namespace. The pod should have a container named `time-check`, using the `busybox` image with the `latest` tag (`busybox:latest`).
    
* Create a config map named `time-config` with the data `TIME_FREQ=12` in the same namespace.
    
* Configure the `time-check` container to run the command: `while true; do date; sleep $TIME_FREQ; done`. Ensure the output is written to `/opt/sysops/time/time-check.log`. Add an environment variable `TIME_FREQ` in the container, getting its value from the config map `TIME_FREQ` key.
    
* Create a volume `log-volume` and mount it at `/opt/sysops/time` within the container.
    

### Steps

1. Create a manifest file `time-check.yaml`.
    
    ```yaml
    apiVersion: v1
    kind: Namespace
    metadata:
      name: devops
    ---
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: time-config
      namespace: devops
    data:
      TIME_FREQ: "12"
    ---
    apiVersion: v1
    kind: Pod
    metadata:
      name: time-check
      namespace: devops
    spec:
      containers:
        - name: time-check
          image: busybox:latest
          command: ["sh", "-c", "while true; do date >> /opt/sysops/time/time-check.log; sleep $TIME_FREQ; done"]
          env:
            - name: TIME_FREQ
              valueFrom:
                configMapKeyRef:
                  name: time-config
                  key: TIME_FREQ
          volumeMounts:
            - name: log-volume
              mountPath: /opt/sysops/time
      volumes:
        - name: log-volume
          emptyDir: {}
    ```
    
    ```bash
    cat << EOF > time-check.yaml
    apiVersion: v1
    kind: Namespace
    metadata:
      name: devops
    ---
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: time-config
      namespace: devops
    data:
      TIME_FREQ: "12"
    ---
    apiVersion: v1
    kind: Pod
    metadata:
      name: time-check
      namespace: devops
    spec:
      containers:
        - name: time-check
          image: busybox:latest
          command: ["sh", "-c", "while true; do date >> /opt/sysops/time/time-check.log; sleep \$TIME_FREQ; done"]
          env:
            - name: TIME_FREQ
              valueFrom:
                configMapKeyRef:
                  name: time-config
                  key: TIME_FREQ
          volumeMounts:
            - name: log-volume
              mountPath: /opt/sysops/time
      volumes:
        - name: log-volume
          emptyDir: {}
    EOF
    ```
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729180872302/711da3b2-a07a-4942-ab0e-13c28986c37d.png align="center")
    
    Now apply
    
    ```bash
    kubectl apply -f time-check.yaml
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729181012497/f9673bd7-cce2-416d-bb50-8df8f7134ddf.png align="left")
    
3. ss