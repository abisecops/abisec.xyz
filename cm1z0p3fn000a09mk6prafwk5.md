---
title: "Change EC2 Instance Type"
seoTitle: "Switching EC2 Instance Type"
seoDescription: "Learn how to change an AWS EC2 instance type from t2.micro to t2.nano, ensuring it stays in a running state"
datePublished: Mon Oct 07 2024 12:57:59 GMT+0000 (Coordinated Universal Time)
cuid: cm1z0p3fn000a09mk6prafwk5
slug: change-ec2-instance-type
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728304375914/ad1fe841-de84-4619-a8fd-f7334c448a8e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728305707886/8206633c-7364-4879-9f70-4d03368c58b7.png
tags: cloud, ec2, aws, cloud-computing, devops, amazon-web-services, ec2-instance-types, ec2-instance

---

### Tasks

* Change the instance type from `t2.micro` to `t2.nano` for `devops-ec2` instance
    
* Make sure the ec2 instance `devops-ec2` is in `running` state after the change.
    

### Steps

1. As we already have a instance name devops-ec2 with t2.micro on running state.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728304717141/c10422f5-672a-4a95-97d6-22e65d59a95f.png align="center")
    
    First stop the running instance.
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728304781790/a1103d37-718f-4b11-bd62-7b0db73e6432.png align="center")
    
    It may took few time to stop. You may see stopping in your instance, wait till the instance be completely stopped.
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728304913759/6a96f492-b48a-4862-b0c7-a9e1627c93a3.png align="center")
    
    Select the instance and click actions → Instance Settings → Change Instance type.
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728304968383/191c9b2f-fea3-4d5b-8f88-972743230ae2.png align="center")
    
    Now change he instance type from `t2.micro` to `t2.nano`
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728305070577/9b6d6f67-706a-4c78-850f-bae10c0b0a77.png align="center")
    
    Please checkout **Instance type comparison** and click **change**.
    
7. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728305125700/3f83219c-e974-4f0f-a21c-c54fe81bcd60.png align="center")
    
    See the changes now but this is on stopped state.
    
8. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728305207314/e4a0b5c0-b36a-4d02-a668-d130b5f9b916.png align="center")
    
    Now start the instance and wait for `running` state after the change.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728305482857/f7deebd6-6134-40ac-be62-6f61b44b124b.png align="center")
    
    #aws
    
    #EC2Instancetypes
    
    #happylearning