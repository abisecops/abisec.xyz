---
title: "Create Publicly Accessible RDS Instance"
seoTitle: "Public RDS Instance Guide"
seoDescription: "Learn to create a publicly accessible MySQL RDS instance using AWS free tier, complete with step-by-step instructions"
datePublished: Tue Oct 08 2024 17:19:18 GMT+0000 (Coordinated Universal Time)
cuid: cm20pgzwi000008k14t4ic1gk
slug: create-publicly-accessible-rds-instance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728402878528/df9f18c9-6bb6-41f2-b037-ba04f382661f.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728407937475/d758a771-6f9e-488d-995d-26a08d07f9c9.png
tags: cloud, aws, cloud-computing, devops, amazon-web-services, devops-articles

---

### Tasks

For this task, create one `publicly` accessible RDS instance using a free tier template along with the following details:

* The name of the RDS instance must be `xfusion-rds`.
    
* The engine type must be `MySQL v8.0.36`, and it must be a `db.t3.micro` type instance.
    
* The master username must be `xfusion_admin` and set some appropriate password.
    
* RDS storage type must be `gp2` and storage size must be `5GiB`.
    
* Keep the rest of the configurations as `default`. Finally, make sure the instance is in `available` state before submitting this task.
    

### Steps

1. RDS → Create database
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728406682131/6b7774a3-1afe-48a9-acfb-7fb409662c6c.png align="center")
    
2. Select free tier template
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728406719240/b2999ed0-1f79-47bc-9812-6144741df3a1.png align="center")
    
    RDS storage = `gp2` and storage size = `5GiB`.
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728406854873/4aa69c95-5ea6-432e-ba88-8506593948df.png align="center")
    
    Everything is going well, but I forgot to select **Publicly Accessible**. I'll modify it now.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728407517743/da7cf461-715b-43a1-a095-c2d7d7b0dfd5.png align="center")
    
5. Connectivity → Public access → Publicly accessible
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728407654599/bd9bcb39-284b-4bcf-aa86-959f3fa4fad8.png align="center")
    
    RDS → Databases → Modify DB instance: xfusion-rds
    
7. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728407731008/01f36d81-edd2-44bb-8e69-be88245e37fc.png align="center")
    
    Our RDS instance is `publicly` accessible now.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728407821280/9689e109-98ff-4b8f-afa6-169aa17808ea.png align="center")
    
    #aws #cloudcomputing #happylearning