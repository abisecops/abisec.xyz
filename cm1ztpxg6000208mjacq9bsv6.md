---
title: "Attach Elastic Network Interface to EC2 Instance"
seoTitle: "Attach ENI to EC2 Instance Easily"
seoDescription: "Learn how to attach an Elastic Network Interface to your EC2 instance with step-by-step instructions in this AWS guide"
datePublished: Tue Oct 08 2024 02:30:27 GMT+0000 (Coordinated Universal Time)
cuid: cm1ztpxg6000208mjacq9bsv6
slug: attach-elastic-network-interface-to-ec2-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728321308269/88e76439-a840-4932-97de-2917b949ae0e.png
tags: cloud, aws, cloud-computing, devops, amazon-web-services, networking, aws-elastic-ip

---

### Tasks

An instance named `devops-ec2` and an elastic network interface named `devops-eni` already exists in `us-east-1` region.

* Attach the `devops-eni` network interface to the `devops-ec2` instance.
    
* Make sure status is `attached` before submitting the task.
    

Please make sure instance initialization has been completed before submitting this task.

### Steps

1. We can see given instance `devops-ec2` is running
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728321662353/fa3b14bf-0d8c-446e-93b5-406a2e6bac33.png align="center")
    
    Select the instance and actions → Networking → Attach Network Interface
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728322093513/4c5b96e2-71f3-4ce7-87e6-63b7061e65de.png align="center")
    
3. Select the given network interface
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728322178478/1ce21f83-c829-4f97-83e1-48dfd2ed4681.png align="center")
    
    Lets attach the `devops-eni` network interface to the `devops-ec2` instance.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728322306591/ec8c10d6-3d71-4e87-ae62-5f6e042fb0f9.png align="center")
    
    * Successfully attached network interface eni-09ed3171880f8103c to instance i-097dbe018aa801707.
        
    
    #aws
    
    #cloud\_computing
    
    #happy\_learning