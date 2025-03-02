---
title: "Create a Lambda Function"
seoTitle: "Guide to Creating a Lambda Function"
seoDescription: "Learn how to create an AWS Lambda function, configure Python runtime, and establish an IAM role for automated serverless computing"
datePublished: Sun Mar 02 2025 11:18:31 GMT+0000 (Coordinated Universal Time)
cuid: cm7rjfjyt000009l2gmmw8749
slug: create-a-lambda-function
tags: cloud, aws, cloud-computing, devops, aws-lambda

---

## AWS Lambda

* <mark>A serverless computing service from Amazon Web Services (AWS) that runs your code in response to events, automatically managing the infrastructure. It scales automatically and charges only for the compute time used.</mark>
    
    ### Tasks
    
    * **Create Lambda Function:** Create a Lambda function named `xfusion-lambda`.
        
    * **Runtime:** Use the Runtime `Python`.
        
    * **Deploy:** The function should print the body `Welcome to KKE AWS Labs!`.
        
    * **Status Code:** Ensure the status code is `200`.
        
    * **IAM Role:** Create and use the IAM role named `lambda_execution_role`.
        
    
    Use the AWS Console to complete this task.
    

### Steps:

1. Create a IAM role named lamda\_exectution\_role.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740912958883/acc8f9de-d50d-4f21-a040-8b8e1cc908ca.png align="center")
    
    **  
    Select trusted entity**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913121994/c4c8ae1e-9d13-485b-8254-d1f064d654a3.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913196444/71f363d7-89a0-493c-9e0c-8cccf7a4360c.png align="center")
    
    **Add permissions**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913348100/d3cad66a-c05d-4607-bba6-db54361378ed.png align="center")
    
    **Name, review,** **and create**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913396171/29451464-7328-4e66-9c55-34889f9ec79b.png align="center")
    
2. lambda\_execution\_role
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913675005/4cfe3be5-caf7-424b-98fc-1ea034b6bc18.png align="center")
    
3. Lambda → Functions → Create function
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913815547/9383905f-6e80-4473-8ce1-ca2917999d2c.png align="center")
    
4. Create Lambda function now
    
5. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1740913998935/9df7b027-d61e-4440-bacb-2d359ba3fdae.png align="center")
    

#happylearning #cloud #aws #lamda