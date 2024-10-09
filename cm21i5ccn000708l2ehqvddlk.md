---
title: "Upgrade RDS MySQL Engine Version via AWS Console"
seoTitle: "Upgrade MySQL in RDS Using AWS Console"
seoDescription: "Upgrade RDS MySQL from 8.0.32 to 8.0.36 via AWS Console, ensuring immediate effect and availability"
datePublished: Wed Oct 09 2024 06:42:03 GMT+0000 (Coordinated Universal Time)
cuid: cm21i5ccn000708l2ehqvddlk
slug: upgrade-rds-mysql-engine-version-via-aws-console
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728454711333/5ca77450-f962-4490-80e1-aa830a09f869.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728456105633/8cbd2956-4e89-4e79-88ea-2a9630d5dc81.png
tags: cloud, aws, cloud-computing, amazon-web-services, rds

---

### Tasks

* Identify the current MySQL version running on the RDS instance `devops-rds` as `8.0.32`.
    
* Plan to upgrade the RDS MySQL engine from version `8.0.32` to `8.0.36`.
    
* Ensure the changes take effect immediately.
    
* Confirm that the RDS instance remains in the `Available` state after the upgrade.
    

### Steps

1. RDS → Databases
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728455268950/a4e5d5a2-fb6e-4741-81c7-fd742fc838aa.png align="center")
    
    RDS → Databases → Modify DB instance: devops-rds
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728455826200/e79a7779-0047-49d9-81e3-abad70a78c46.png align="center")
    
    Schedule modifications → Apply immediately → Modify DB instance
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728455890995/a21e0e6f-287d-4ca1-b6a3-837b248a2830.png align="center")
    
    Successfully modified **devops-rds**.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728455970635/1d87e58a-b926-417d-9d01-e3593f513f6e.png align="center")
    
    #aws #cloudcomputing #happylearning