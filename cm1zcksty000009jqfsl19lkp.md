---
title: "Attach Elastic IP to EC2 Instance"
seoTitle: "Assign Elastic IP to EC2 Instance"
seoDescription: "Learn how to attach an Elastic IP to an EC2 instance in AWS with step-by-step instructions"
datePublished: Mon Oct 07 2024 18:30:34 GMT+0000 (Coordinated Universal Time)
cuid: cm1zcksty000009jqfsl19lkp
slug: attach-elastic-ip-to-ec2-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728307989025/d4e3391c-8fdb-485c-8a24-ddf240a704af.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728308695274/728da1db-c9dc-42be-9850-29fae9d1b5f3.png
tags: cloud, aws, cloud-computing, amazon-web-services

---

### Tasks

* There is an instance named `xfusion-ec2` and an elastic-ip named `xfusion-ec2-eip` in `us-east-1` region. Attach the `xfusion-ec2-eip` elastic-ip to the `xfusion-ec2` instance.
    

### Steps

1. We have Elastic IP addresses.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728308204736/b258851c-3318-4377-acdb-8d81ac7c124e.png align="center")
    
    Follow this steps : [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Home:) → [Elastic IP addresses](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Addresses:) → **Associate Elastic IP address**
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728308520542/2f1c86f9-1949-4e32-b907-83c7aef05bec.png align="center")
    
    Allocate running instance and assocate now.
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728308542250/3d136a98-90ac-4376-bbb2-41abefd14d28.png align="center")
    
    **Elastic IP address associated successfully.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728308627798/4534866a-8ec0-4bc9-adb5-56a6dda07a16.png align="center")