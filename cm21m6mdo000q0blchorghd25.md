---
title: "Create Private S3 Bucket via AWS CLI"
seoTitle: "Create Private S3 Bucket Using AWS CLI"
seoDescription: "Learn how to create a private AWS S3 bucket using AWS CLI, including setting up and blocking public access"
datePublished: Wed Oct 09 2024 08:35:01 GMT+0000 (Coordinated Universal Time)
cuid: cm21m6mdo000q0blchorghd25
slug: create-private-s3-bucket-via-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728461697812/f9d84bab-d932-4124-a83f-5d5ad649685d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1728462887900/7a5d6d60-6916-4402-9d74-75b602d9b1de.png
tags: cloud, aws, cloud-computing, amazon-web-services, s3

---

### Tasks

Create a S3 bucket through `aws-cli` with the following details:

* The name of the S3 bucket must be `xfusion-s3-29022`.
    
* The S3 bucket must block all `public` access, i.e., it must be a `private` bucket.
    

### Steps

1. Create the S3 bucket named `xfusion-s3-29022` in the `us-east-1` region:
    
    ```bash
    aws s3api create-bucket --bucket xfusion-s3-29022 --region us-east-1
    ```
    
2. Block all public access to the bucket to make it private:
    
    ```bash
    aws s3api put-public-access-block \
    --bucket xfusion-s3-29022 \
    --public-access-block-configuration BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true
    ```
    
3. AWS CLI
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728462728989/8523c670-b0e9-4c3c-ad9e-6fdba69abf06.png align="center")
    
4. Verify now.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728462829246/20137f7d-c08a-4dd3-b321-f51559373c1e.png align="center")
    
    #aws #cloudcomputing #happylearning