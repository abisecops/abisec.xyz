---
title: "Create IAM Role for EC2 with Policy Attachment"
seoTitle: "Create EC2 IAM Role with Policy Guide"
seoDescription: "Learn how to create an IAM role for EC2 with policy attachment in AWS with step-by-step instructions"
datePublished: Tue Oct 08 2024 08:09:11 GMT+0000 (Coordinated Universal Time)
cuid: cm205tjur000f0aky7g8kfx50
slug: create-iam-role-for-ec2-with-policy-attachment
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728373595038/0f1e9eba-24ab-4afd-95d5-eb5114492180.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728374925613/08d0ee95-7749-453c-9ef2-6389b6474e4b.png
tags: cloud, aws, cloud-computing, devops, amazon-web-services, devops-articles

---

### Tasks

Create an IAM role as below:

* IAM role name must be `iamrole_javed`.
    

* Entity type must be `AWS Service` and use case must be `EC2`.
    
* Attach a policy named `iampolicy_javed`.
    

### Steps

1. IAM → Roles → Create role now
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728374357710/47b519d0-11a5-4ded-b524-5eb2e2b4e313.png align="center")
    
    Trusted entity type → AWS Service | Service or use case → EC2
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728374424897/588cacd4-6983-4dd0-a871-b951fac53074.png align="center")
    
    Add permissions and Role name → iamrole\_javed
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728374717385/b38a0cb4-0de6-4b8c-a0c1-1c417849765e.png align="center")
    
    **Create Role** now
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728374781464/aa462d31-7b2e-41f0-8c33-da890229a5eb.png align="center")
    
    **Role iamrole\_javed is created.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728374828400/1dd39096-6a6f-4c64-90b6-5385b3442f09.png align="center")
    
    #happylearning #aws #cloudcomputing