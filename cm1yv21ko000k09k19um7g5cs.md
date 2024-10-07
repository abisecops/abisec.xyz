---
title: "Create Security Group"
seoTitle: "How to Create a Security Group"
seoDescription: "Learn how to create a security group for Nautilus App Servers, including setting up HTTP and SSH inbound rules"
datePublished: Mon Oct 07 2024 10:20:05 GMT+0000 (Coordinated Universal Time)
cuid: cm1yv21ko000k09k19um7g5cs
slug: create-security-group
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728295408588/62f05cdd-c211-448d-95bf-5e6447d3364b.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728296390283/8127c311-5d9d-4e7d-aaa2-9fa4c03afbda.png
tags: cloud, aws, cloud-computing, amazon-web-services, securitygroups

---

## Table of contents

### Tasks:

For this task, create a security group under default VPC with the following requirements:

* Name of the security group is `datacenter-sg`.
    
* The description must be `Security group for Nautilus App Servers`
    
* Add the inbound rule of type `HTTP`, with port range of `80`. Enter the source CIDR range of `0.0.0.0/0`.
    
* Add another inbound rule of type `SSH`, with port range of `22`. Enter the source CIDR range of `0.0.0.0/0`.
    

### Steps:

1. Find the service: Security Groups
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728296334889/e4344298-49ab-4870-b44d-10e257fc61f5.png align="center")
    
2. Give name for security group and description
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728295988186/1c346442-2855-44ad-918e-cac7ff91966b.png align="center")
    
3. Inbound rules for http and ssh:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728296023675/87c85dab-22c3-410a-b702-40d858a16d39.png align="center")
    
4. Security group was created successfully
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728296076516/bff35604-98d2-437d-80c7-3ffb89be1287.png align="center")
    
    #aws
    
    #security\_group
    
    #happylearning