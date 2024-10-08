---
title: "Transfer Data to Existing S3 Bucket"
seoTitle: "Move Data into Existing S3 Bucket"
datePublished: Tue Oct 08 2024 12:43:58 GMT+0000 (Coordinated Universal Time)
cuid: cm20fmx7l000f0al3ft4s297s
slug: transfer-data-to-existing-s3-bucket
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728390559162/25a1774e-5e63-4500-8cba-c660c4753539.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728391429595/8b14b43c-1bc7-43a8-9ea6-c8aef22d3f0f.png
tags: cloud, aws, cloud-computing, amazon-web-services, aws-cli, s3-bucket

---

### Tasks

* S3 bucket named `xfusion-cp-7889` already exists. Copy the file `/tmp/xfusion.txt` to s3 bucket `xfusion-cp-7889`.
    

### Steps

1. First of all checkout the s3 bucket, to ensure this is already exists.
    
    * Amazon S3 → Buckets → xfusion-cp-7889
        
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728391085175/67f07174-d92b-4a0e-b20f-f516fa765b32.png align="center")
    
    Verify the file on path, /tmp/xfusion.txt
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728391164336/a1f7ddb6-d18b-4ea8-afce-f80fa9e7dfdc.png align="center")
    
    Now use command
    

```bash
aws s3 cp /tmp/xfusion.txt s3://xfusion-cp-7889/
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728391296421/3546f164-b75d-4b99-bfb5-ac6f91e1ba50.png align="center")

4. Refresh and check, we can see the txt file is copied to S3 bucket.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728391332302/ca552b52-c833-4f2a-830b-fea8b30480c1.png align="center")
    
    #aws #cloudcomputing #happylearning