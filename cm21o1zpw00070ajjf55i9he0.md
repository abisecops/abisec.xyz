---
title: "Delete EC2 Instance via AWS CLI"
seoTitle: "AWS CLI: Delete EC2 Instance Guide"
seoDescription: "Learn how to delete an EC2 instance using AWS CLI, including instance termination verification"
datePublished: Wed Oct 09 2024 09:27:24 GMT+0000 (Coordinated Universal Time)
cuid: cm21o1zpw00070ajjf55i9he0
slug: delete-ec2-instance-via-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728465483881/bd98f6f4-dd54-44c5-b680-b56f5e7b8fdb.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728466029367/05617099-bd1b-4127-9fdb-b0c3cc88bae8.png
tags: cloud, ec2, linux, aws, cloud-computing, devops, aws-cli

---

### Tasks

* Using AWS CLI, delete an EC2 instance named `nautilus-ec2` present in the `us-east-1` region.
    
* Before submitting your task, make sure the instance is in the `terminated` state.
    

### Steps

1. Get the instance ID and Stop the `nautilus-ec2` instance.
    
    ```bash
    aws ec2 describe-instances --filters "Name=tag:Name,Values=nautilus-ec2" --query "Reservations[*].Instances[*].InstanceId" --output text
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728465737660/1bfebb72-46ea-4525-bae3-1f64fcb9d882.png align="center")
    
    * **i-04575360679a33d0b**
        
2. Delete the EC2 Instance
    
    ```bash
    aws ec2 terminate-instances --instance-ids i-04575360679a33d0b --region us-east-1
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728465874908/5aef0903-a843-4f60-9624-1b2e29040155.png align="center")
    
3. Verify the instance state is on terminated state
    
    ```bash
    aws ec2 describe-instances --instance-ids i-04575360679a33d0b --region us-east-1 --query "Reservations[*].Instances[*].State.Name" --output text
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728465957596/35a33db4-bc38-4b14-be87-556829628aac.png align="center")
    
    #aws #cloudcomputing #happylearning