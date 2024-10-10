---
title: "Expanding EC2 Instance Storage for Development Needs"
seoTitle: "Increase EC2 Storage for Development"
seoDescription: "Learn how to expand AWS EC2 instance storage from 8 GiB to 12 GiB for development needs with this guide"
datePublished: Thu Oct 10 2024 17:57:54 GMT+0000 (Coordinated Universal Time)
cuid: cm23lqc71000l09l6hykc9h0j
slug: expanding-ec2-instance-storage-for-development-needs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728580174508/1b8c15f2-5651-4563-9c18-33ef80a7ff67.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728583058756/edee16ef-d6ea-4f25-b7c0-fe74e76cfd00.png
tags: cloud, aws, cloud-computing, amazon-web-services, storage

---

### Tasks

* **Identify Volume:** Find the volume attached to the `xfusion-ec2` instance.
    
* **Expand Volume:** Increase the volume size from `8 GiB` to `12 GiB`.
    
* **Reflect Changes:** Ensure the root (`/`) partition within the instance reflects the expanded size from `8 GiB` to `12 GiB`.
    
* **SSH Access:** Use the key pair located at `/root/xfusion-keypair.pem` on the `aws-client` host to SSH into the EC2 instance.
    

### Steps

1. We already have **Instances,** `xfusion-ec2`.
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728582181471/15bd741b-e21d-43c2-91c1-7ea3b32dfdd3.png align="center")
    
    EC2 → Volumes → vol-044ea2f7bad002711 → Modify volume
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728582335887/e1e2a470-c354-42bd-b735-5fbe0fe41d60.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728582375622/2f738ca3-95db-406f-83e0-c45a5d0d0f71.png align="center")
    
    Modify vol-044ea2f7bad002711 → Modify
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728582410472/d72c3ab0-7a2f-4220-85eb-c8949abc1c15.png align="center")
    
    Pem files stored at /root/xfusion-keypair.pem.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728582533285/da624c50-f126-4c20-a676-3795b3368d5a.png align="center")
    
5. Verify the Partition Size on the EC2 Instance
    

```bash
sudo growpart /dev/xvda 1
```

6. Resize the Filesystem
    
    ```bash
    sudo xfs_growfs /
    ```
    
7. Verify the Resized Filesystem
    
    ```bash
    df -h
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728583007349/e42921c1-38c4-4154-874e-728bbd83df61.png align="center")