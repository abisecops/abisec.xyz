---
title: "Attach Volume to EC2 Instance"
seoTitle: "Attach AWS Volume to EC2 Instance"
seoDescription: "Learn to attach an existing EBS volume to an EC2 instance in the AWS console effortlessly"
datePublished: Tue Oct 08 2024 02:32:21 GMT+0000 (Coordinated Universal Time)
cuid: cm1ztse0b000308mj4omw68gq
slug: attach-volume-to-ec2-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728322832293/fd74b79e-62a6-468b-82c0-017a33c0933d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728326695387/d1fe9650-5288-4c96-a9c8-0f1a6c2d5030.png
tags: cloud, aws, cloud-computing, devops, amazon-web-services, amazon-ec2, volume

---

### Tasks

* An instance named `datacenter-ec2` and a volume named `datacenter-volume` already exists in `us-east-1` region. Attach the `datacenter-volume` volume to the `datacenter-ec2` instance, make sure to set the device name to `/dev/sdb` while attaching the volume.
    

### Steps

1. Instance `datacenter-ec2` is running state.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728326176837/8bf795ae-4b58-4688-9f68-e0f5953d1249.png align="center")
    
2. Given volume is also exist
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728326275176/73e7d569-bd2f-49f5-b50f-127d884a7a3e.png align="center")
    
    * [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Home:) → [Vol](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Volumes:)[ume](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Home:)[s](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Volumes:) →
        
3. Select Attach Volume
    
    [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Home:) → [Volumes](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Volumes:) → [vol-009b9a40a513a7719](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#VolumeDetails:volumeId=vol-009b9a40a513a7719) → [**Attach volume**](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#VolumeDetails:volumeId=vol-009b9a40a513a7719)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728323898732/6f8e515d-c700-4cc3-9365-1cda10cf3d60.png align="center")
    
4. Select the running instance `datacenter-ec2`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728326415704/80c4a381-0eff-4dbf-81ff-f08af70aa673.png align="center")
    
5. Device name `/dev/sdb` and attach now
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728326484175/dfe92394-b2bd-4c8f-8ab0-6c579d4738c5.png align="center")
    
6. * Successfully attached volume [vol-009b9a40a513a7719](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#VolumeDetails:volumeId=vol-009b9a40a513a7719) to instance [i-0194b76b228219098](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#InstanceDetails:instanceId=i-0194b76b228219098).
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728326554225/4b7f5853-cf88-4970-85f8-e4af33084a58.png align="center")
    
    #cloudcomputing
    
    #happylearning #aws