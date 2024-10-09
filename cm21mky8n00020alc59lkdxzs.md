---
title: "Launch EC2 Instance via AWS CLI"
seoTitle: "AWS CLI: Launch EC2 Instance Guide"
seoDescription: "Learn how to launch an EC2 instance using AWS CLI with a specific AMI, instance type, and a new RSA key pair"
datePublished: Wed Oct 09 2024 08:46:10 GMT+0000 (Coordinated Universal Time)
cuid: cm21mky8n00020alc59lkdxzs
slug: launch-ec2-instance-via-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728463072573/e63b0b6a-067a-432e-84ac-d054952b3e2c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728463556604/1a749e60-601c-4810-9f2e-76902d9ec16c.png
tags: cloud, ec2, trends, aws, cloud-computing, devops

---

### Tasks

Create an EC2 instance using AWS CLI under default VPC with the following details:

* The name of the instance must be `datacenter-ec2`.
    
* You can use the `ami-0cd59ecaf368e5ccf` AMI to launch this instance.
    
* The instance type must be `t2.micro`.
    
* Create a new RSA key pair named `datacenter-kp`.
    
* Attach the default security group (available by default).
    

### Steps

1. Create a new RSA key pair named `datacenter-kp`:
    
    ```bash
    aws ec2 create-key-pair --key-name datacenter-kp --query 'KeyMaterial' --output text > datacenter-kp.pem
    ```
    
2. Launch an EC2 instance with the specified AMI and instance type, and assign it the name `datacenter-ec2`:
    
    ```bash
    aws ec2 run-instances --image-id ami-0cd59ecaf368e5ccf --count 1 --instance-type t2.micro --key-name datacenter-kp --security-groups default --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=datacenter-ec2}]'
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728463416642/8ffa7bba-6b66-4d20-807b-4768ede22ca5.png align="center")
    
3. Ensure the key pair file has the correct permissions:
    
    ```bash
    chmod 400 datacenter-kp.pem
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728463496625/f334d3d9-c9f3-42c9-b05f-f8e6b91be043.png align="center")
    
    #aws #cloudcomputing #happylearning