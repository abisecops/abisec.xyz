---
title: "Configuring a Public VPC with an EC2 Instance for Internet Access"
seoTitle: "Set Up Public VPC and EC2 for Internet Access"
seoDescription: "Learn to configure a public VPC with an EC2 instance for internet access, including subnet, security groups, and route tables"
datePublished: Mon Dec 09 2024 15:35:37 GMT+0000 (Coordinated Universal Time)
cuid: cm4h72hka000j09kwb6gt1o8j
slug: configuring-a-public-vpc-with-an-ec2-instance-for-internet-access
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1733749725280/d90436a3-4713-45d5-a647-d4c6f9c374ac.png
tags: cloud, aws, cloud-computing, devops, amazon-web-services, vpc

---

### Tasks

* Create a public VPC named `devops-pub-vpc`.
    
* Create a subnet named `devops-pub-subnet` under the VPC.
    
* Ensure public IPs are automatically assigned to resources in this subnet.
    
* Create an EC2 instance named `devops-pub-ec2` under this VPC.
    
* Ensure SSH port `22` is open for this instance and accessible over the internet.
    
    ### Steps
    
    1. Create a VPC now.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733755210049/9323ef9c-dc5a-474a-974a-e9366bf842be.png align="center")
        
    2. VPC → Your VPCs → Create VPC
        
        Enter the following details:
        
        * **Name tag**: `devops-pub-vpc`
            
        * **IPv4 CIDR block**: `10.0.0.0/16`
            
        * **IPv6 CIDR block**: No IPv6 CIDR block.
            
        * **Tenancy**: Default
            
            *Click* ***Create VPC****.*
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733755457079/b1dc1192-17e7-46ca-a68a-87dd79916798.png align="center")
        
    3. You successfully created vpc-0fe2735e948ae693d / devops-pub-vpc.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733755590307/4ef0c37c-07f1-4a0f-a838-812166abd265.png align="center")
        
    4. Enable Public DNS for the VPC
        
        * Select the newly created VPC (`devops-pub-vpc`) in the VPC dashboard.
            
        * Go to the **Actions** dropdown and choose **Edit DNS hostnames**.
            
        * Enable both **DNS resolution** and **DNS hostnames**.
            
        * Save changes.
            
            **VPC → Your VPCs → vpc-0fe2735e948ae693d → Edit VPC settings**
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733755791111/1ee7bc82-2a9c-4b8f-ad9c-150e9f9de2dc.png align="center")
            
    5. ### **Create the Subnet**
        
        a) In the VPC Dashboard, click **Create Subnet**.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733755989579/7f5dd2e8-1dd5-4633-8105-ddc15bfed03e.png align="center")
        
        b) Enter the following details:
        
        * **VPC**: Select `devops-pub-vpc`.
            
        * **Subnet name**: `devops-pub-subnet`.
            
        * **Availability Zone**: Select any (e.g., `us-east-1a`).
            
        * **IPv4 CIDR block**: `10.0.1.0/24`.
            
        
        **VPC → Subnets → Create subnet**
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756232715/0876974b-5e36-4994-bd3a-f29f4c9cdbc0.png align="center")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756310011/87200f03-3477-47fd-94cb-8c387f7f6b09.png align="center")
        
    6. Enable **Auto-assign public IPv4 address**.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756463730/19bfdfbb-68db-4e66-9469-b632e0244bf6.png align="center")
        
    7. Create an **Internet Gateway**
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756854212/15609fe0-99f8-43bc-be51-d76c17509e18.png align="center")
        
    8. Go to **Actions**, and choose **Attach to VPC**.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756929892/f5c37b39-be77-4eaf-bd93-a1d0b3e1f2dd.png align="center")
        
    9. Select devops-pub-vpc and click Attach internet gateway.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733756994241/8a1d1ddb-42bb-4ac1-8eb5-52c8cdbeb5a3.png align="center")
        
    10. Create and Configure a Route Table
        
        * In the VPC Dashboard, go to **Route Tables**.
            
        * Click **Create route table**.
            
        * Enter the following details:
            
            * **Name tag**: `devops-pub-rt`
                
            * **VPC**: Select `devops-pub-vpc`.
                
        * Click **Create route table**.
            
            **VPC → Route tables → Create route table**
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733757143719/c0390299-5a09-4b17-a77b-aea2f2bf15d2.png align="center")
            
    11. Click Edit routes.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733757254608/a78c5b22-10c8-463c-bec4-eb20d0ae1ec1.png align="center")
        
    12. Add the following route:
        
        * **Destination**: `0.0.0.0/0`
            
        * **Target**: Internet Gateway (select `devops-igw` from the dropdown).
            
        * Save changes.
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733757408889/13e08925-a184-469a-946d-6a3cac0bc569.png align="center")
        
    13. Edit subnet associations
        
        VPC → Route tables → rtb-005a434e2701bf060 → Edit subnet associations
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733757547208/fc772f77-e390-4936-a0b1-50a3aecac995.png align="center")
        
    14. Create a **Security Group**
        
        Enter the following details:
        
        * **Security group name**: `devops-pub-sg`
            
        * **Description**: Allow SSH access.
            
        * **VPC**: Select `devops-pub-vpc`.
            
    15. Add an **Inbound Rule**:
        
        * **Type**: SSH
            
        * **Protocol**: TCP
            
        * **Port Range**: 22
            
        * **Source**: `0.0.0.0/0`
            
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733757850240/f2406381-7020-4200-980d-0d55c3529b77.png align="center")
        
    16. ### **Launch the EC2 Instance**
        
        * Go to the **EC2 Dashboard** and click **Launch Instances**.
            
        * Enter the following details:
            
            * **Name**: `devops-pub-ec2`.
                
            * **AMI**: Any of ami ( I am choosing ubuntu right now)
                
            * **Instance type**: `t2.micro`.
                
            * **Key pair**: Select an existing key pair or create a new one.
                
            * **Network settings**:
                
                * **VPC**: Select `devops-pub-vpc`.
                    
                * **Subnet**: Select `devops-pub-subnet`.
                    
                * **Auto-assign public IP**: Enabled (should be automatic due to subnet settings).
                    
                * **Security group**: Select `devops-pub-sg`.
                    
        * Click **Launch Instance**.
            
        
        1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733758110060/ba849ca5-2965-455e-8031-8b36f3ba100c.png align="center")
            
            **Congrats!** You have successfully completed the task.