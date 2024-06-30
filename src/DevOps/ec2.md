# Static Website Deployment Guide

This guide will walk you through the steps to deploy a static website on an AWS EC2 instance using NGINX.

## Step 1: Update the Package List

First, ensure your package list is up to date.

```bash
sudo yum update -y
```

# Step 2: Install Git
## Install Git to clone your repository.
```bash
sudo yum install git -y
```

# Step 3: Clone Your Repository
## Clone your repository to the EC2 instance.
```bash
git clone https://github.com/your-username/your-repository.git

```

# Step 4: Install NGINX
## Install NGINX web server.

```bash
sudo amazon-linux-extras install nginx1 -y
```
# Step 5: Start and Enable NGINX
## Start the NGINX service and enable it to start on boot.

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```
# Step 6: Remove Default NGINX Content
## Remove the default content served by NGINX.

```bash
sudo rm /usr/share/nginx/html/*
```
# Step 7: Copy Your Website Files to NGINX Directory
## Copy your static website files to the NGINX root directory.

```bash
sudo cp -r your-repository/* /usr/share/nginx/html/
```
### Replace your-repository with the name of your cloned repository folder.

# Step 8: Set Permissions
## Ensure the website files have the correct permissions.

```bash
sudo chmod -R 755 /usr/share/nginx/html
```
# Step 9: Configure NGINX
## Open the NGINX configuration file to update the server block.

```bash
sudo nano /etc/nginx/nginx.conf
```
### Update the server block to look like this:

```bash
server {
    listen       80;
    server_name  your-domain.com;  # If you have a domain, replace with your domain name

    location / {
        root   /usr/share/nginx/html;
        index  index.html index.htm;
    }

    error_page  404              /404.html;
    location = /404.html {
        internal;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        internal;
    }
}

```
### Replace your-domain.com with your actual domain name if you have one. If not, leave it as is.

# Step 10: Test NGINX Configuration
## Test the NGINX configuration for syntax errors.

```bash
sudo nginx -t
```
# Step 11: Reload NGINX
## Reload NGINX to apply the changes.

```bash
sudo systemctl reload nginx
```
### Your static website should now be deployed and accessible via your EC2 instance's public IP address.

## Additional Notes
## If you encounter any issues, check the NGINX error logs:

```bash
sudo tail -f /var/log/nginx/error.log
```
### Ensure NGINX is running:

```bash
sudo systemctl status nginx
```

# Conclusion
## By following these steps, you should have successfully deployed a static website on an AWS EC2 instance using NGINX. If you have any questions or run into issues, feel free to ask for help.


### You can save this content into a file named `deployment-guide.md`. This guide includes all the necessa