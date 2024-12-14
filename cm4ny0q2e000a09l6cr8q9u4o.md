---
title: "Custom Apache User Setup"
seoTitle: "Set Up Custom Apache User"
seoDescription: "Learn to create a user with a specific UID and home directory on Apache App server 1 using command line steps"
datePublished: Sat Dec 14 2024 08:56:42 GMT+0000 (Coordinated Universal Time)
cuid: cm4ny0q2e000a09l6cr8q9u4o
slug: custom-apache-user-setup
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1734166719148/1beba79a-7e5b-40b0-90ea-1b95e42c5cb3.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1734166727301/eca35501-ee58-4e1a-bd99-c267fdd8b99e.png
tags: linux, linux-for-beginners, linux-basics, linux-commands

---

### Tasks

Create a user named `ravi` on `App server 1` within the Stratos Datacenter.

* Assign the user a unique UID `1541`.
    
* Set the home directory for the user as `/var/www/ravi`.
    

### Steps

1. First of all let’s get connect with `App server 1` with
    
    * <table><tbody><tr><td colspan="1" rowspan="1"><p>stapp01</p></td><td colspan="1" rowspan="1"><p>172.16.238.10</p></td><td colspan="1" rowspan="1"><p><a target="_self" rel="noopener noreferrer nofollow" href="http://stapp01.stratos.xfusioncorp.com" style="pointer-events: none">stapp01.stratos.xfusioncorp.com</a></p></td><td colspan="1" rowspan="1"><p>tony</p></td><td colspan="1" rowspan="1"><p>Ir0nM@n</p></td><td colspan="1" rowspan="1"><p></p></td></tr></tbody></table>
        
    
    ```bash
    ssh tony@172.16.238.10
    ```
    
    Password: `Ir0nM@n` | Also with:
    
    ```bash
    sshpass -p 'Ir0nM@n' ssh tony@172.16.238.10
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734165875750/94766877-57ba-419a-a279-66b10641c03d.png align="left")
    
2. Create the User with Specific UID and Home Directory
    
    ```bash
    sudo useradd -u 1541 -d /var/www/ravi -m ravi
    ```
    
    * \-`u (UID)`\`
        
    * \-`d (Directory`)
        
    * \-`m` `ensures the home directory is created`
        
3. Verify the user `ravi` with given command.
    
    ```bash
    id ravi
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734166233103/5adfa4f7-451c-4eaf-bf44-95e354a9b56e.png align="left")
    
    Also check the home directory:
    
    ```bash
    ls -ld /var/www/ravi
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734166439630/de1b0d71-679b-48f1-b936-109122c3f4ad.png align="left")
    
    #linux #uid #happylearning