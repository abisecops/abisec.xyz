---
title: "Create Read-Only IAM Policy for EC2 Console Access"
seoTitle: "EC2 Console Read-Only IAM Policy"
seoDescription: "Create a read-only IAM policy for accessing the EC2 console, allowing users to view instances, AMIs, and snapshots"
datePublished: Tue Oct 08 2024 07:00:59 GMT+0000 (Coordinated Universal Time)
cuid: cm203dupk000j09jleol2cet6
slug: create-read-only-iam-policy-for-ec2-console-access
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728369874305/0bf7192a-9682-4105-9d9b-13d29c75bb54.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728370842843/98f6d630-60eb-40d4-acc6-28b9261662df.png
tags: cloud, trends, aws, cloud-computing, devops, amazon-web-services, trending

---

### Tasks

* Create an IAM policy named `iampolicy_rose` in `us-east-1` region, it must allow read-only access to the EC2 console, i.e this policy must allow users to view all instances, AMIs, and snapshots in the Amazon EC2 console.
    

### Steps

1. Select Policies under IAM.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370128999/a01fdcb5-aea7-48ba-9f77-25500f104e10.png align="left")
    
    IAM → Policies → Create Policy
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370204389/b105964a-cb77-421e-b62d-a49c127eb0ae.png align="center")
    
    Specify permissions → **Select a service**
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370313979/0b79decd-4b0e-4c07-aedf-b974c1b33ea2.png align="center")
    
    Read-only access to the EC2 console
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370567943/e0814db0-10ee-421d-af85-2266593b01fe.png align="center")
    
    Name Policy and create
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370679569/0b3bfd2f-d9f2-450f-9ecd-0a4ba91d6796.png align="center")
    
    **Policy iampolicy\_rose created.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728370748785/f2836554-85f4-4a98-8789-ccfd337c8587.png align="center")