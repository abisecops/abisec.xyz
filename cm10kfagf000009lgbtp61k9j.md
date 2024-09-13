---
title: "Hide Nginx Server Information for Better Security"
seoTitle: "Secure Nginx by Hiding Server Info"
seoDescription: "Learn to enhance security by hiding Nginx server information. Follow essential steps for securing your server from potential vulnerabilities"
datePublished: Fri Sep 13 2024 10:18:18 GMT+0000 (Coordinated Universal Time)
cuid: cm10kfagf000009lgbtp61k9j
slug: hide-nginx-server-information-for-better-security
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1726222572213/b4b3a023-3763-452b-ba64-59d8ce068432.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1726222659977/0615087b-4270-4ee6-bd8b-9ae8c85ac3f5.png
tags: server, web-development, nginx, security, devops, securityawareness

---

While deploying APIs on nginx server, we should be aware about future possible vulnerable cases. So better to prevent such possible vulnerability and threats on time.

There are several cves published regularly. In case, attacker know our server info, he/she can test or exploit to our server. So, better to hide them to prevent such cases.

**Steps:**

1. **Install nginx-extras** **and** **Create the custom server name:**
    

```plaintext
sudo apt-get install nginx-extras
```

```plaintext
cd /etc/nginx/sites-available
```

```plaintext
more_set_headers 'Server: hicare'; # To Set a custom string as "Server" 
```

2. Now time to update nginx.conf too:
    

```bash
       #add this on http section
       server_tokens off;
        more_clear_headers Server; 
```

As the below format

```bash
http {

        ##
        # Basic Settings
        ##

        sendfile on;
        tcp_nopush on;
        types_hash_max_size 2048;
        server_tokens off;
        more_clear_headers Server;      

        # server_names_hash_bucket_size 64;
        # server_name_in_redirect off;

        include /etc/nginx/mime.types;
        default_type application/octet-stream;

}
```

3. Now, test and reload nginx server:
    

```bash
sudo nginx -t
sudo nginx -s reload
sudo systemctl restart nginx
```

![](https://devsecops.abisec.xyz/~gitbook/image?url=https%3A%2F%2F3155059101-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Ftpxp8dhlubc3j58Iygn5%252Fuploads%252F2RVmKEygwdOTAyhxorZh%252Fimage.png%3Falt%3Dmedia%26token%3D968370fc-a8aa-427d-9a45-c8d091168105&width=768&dpr=1&quality=100&sign=12b3ac03&sv=1 align="left")