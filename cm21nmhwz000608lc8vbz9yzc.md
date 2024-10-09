---
title: "Modify EC2 Instance Type via AWS CLI"
seoTitle: "Change EC2 Instance Type Using AWS CLI"
seoDescription: "Learn how to change an EC2 instance type using AWS CLI, ensuring it stays running post-modification. Follow these simple steps"
datePublished: Wed Oct 09 2024 09:15:21 GMT+0000 (Coordinated Universal Time)
cuid: cm21nmhwz000608lc8vbz9yzc
slug: modify-ec2-instance-type-via-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728463771040/b73c670a-fde6-4493-84f1-0a48f7977ff2.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728464021059/ced7dc82-516d-49dc-8701-80abb78e0168.png
tags: cloud, aws, cloud-computing, cli, devops

---

### Tasks

* Change the instance type from `t2.micro` to `t2.nano` for the `nautilus-ec2` instance using `aws-cli` only.
    
* Ensure the `nautilus-ec2` instance is in the `running` state after the change.
    

### Steps

1. Get the instance ID and Stop the `nautilus-ec2` instance:
    
    ```bash
    aws ec2 describe-instances --filters "Name=tag:Name,Values=nautilus-ec2" --query "Reservations[*].Instances[*].InstanceId" --output text
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728464688480/161c4360-08ff-4c37-b278-26d087bc38bb.png align="center")
    
    * **i-0a089a6cf430546c4**
        

```bash
aws ec2 stop-instances --instance-ids i-0a089a6cf430546c4
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728464782138/8a7acbab-0711-4406-9c87-ea7ea2ecf41d.png align="center")

2. Wait until the instance is stopped:
    

```bash
aws ec2 wait instance-stopped --instance-ids i-0a089a6cf430546c4
```

3. Change the instance type to `t2.nano`:
    

```bash
aws ec2 modify-instance-attribute --instance-id i-0a089a6cf430546c4 --instance-type "{\"Value\": \"t2.nano\"}"
```

4. Start the `nautilus-ec2` instance:
    

```bash
aws ec2 start-instances --instance-ids i-0a089a6cf430546c4 
```

5. Ensure the instance is in the `running` state:
    
    ```bash
    aws ec2 wait instance-running --instance-ids i-0a089a6cf430546c4
    ```
    
6. Check the instance type now.
    

```bash
aws ec2 describe-instances --instance-ids i-0a089a6cf430546c4 --query "Reservations[*].Instances[*].InstanceType" --output text
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728465207949/4cc34a84-7ce3-4691-aeed-8b8661ae3db6.png align="center")

#aws #cloudcomputing #happylearning