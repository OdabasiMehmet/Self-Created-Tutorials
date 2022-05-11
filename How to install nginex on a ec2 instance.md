# Hands-on EC2-02 : How to Install Nginx Web Server on EC2 Linux 2

## Part 1 - Launching an Amazon Linux 2 EC2 instance and Connect with SSH

1.  Launch an Amazon EC2 instance with AMI as `Amazon Linux 2`, instance type as `t2.micro` and default VPC security group which allows connections from SSH and HTTP.

2. Connect to your instance with SSH.

Option 1 : ssh -i [Your Key pair] ec2-user@[Your EC2 IP / DNS name]
Option 2 : Configurimg remote ssh on VsCode

## Part 2 - Installing and Configuring Nginx Web Server to Run a Simple Web Page

1. Update the installed packages and package cache on your instance.

sudo yum update -y

2. Install the Nginx Web Server.

sudo amazon-linux-extras install nginx1

3. Start the Nginx Web Server.

sudo systemctl start nginx

4. Check from browser with public IP/DNS

5. Go to /usr/share/nginx/html folder.

cd /usr/share/nginx/html

6. Show content of folder and change the permissions of /usr/share/nginx/html

ls

sudo chmod -R 777 /usr/share/nginx/html

7. Remove existing `index.html`.

sudo rm index.html

8. Upload new `index.html` and `ken.jpg` files with `wget` command. Show the github and explain the RAW .

wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/index.html
wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/ken.jpg

9. restart the Nginx Web Server.

sudo systemctl restart nginx

10. configure to start while launching

sudo systemctl enable nginx

11. Check if the Web Server is working properly from the browser.

12. to add another content change the permissions of folder /usr/share/nginx/html.(If you haven't before)

sudo chmod -R 777 /usr/share/nginx/html

13. Add another index.html file 

echo "New Page" > /usr/share/nginx/html/index_2.html

14. Go to your browser and add "/index_2.html" at the end of the the public DNS 


## Part 3 - Automation of Web Server Installation through Bash Script (User data)

15. Configure an Amazon EC2 instance with AMI as `Amazon Linux 2`, instance type as `t2.micro`, default VPC security group which allows connections from SSH and HTTP.

16. Configure instance to automate web server installation with `user data` script.


#! /bin/bash

yum update -y
amazon-linux-extras install nginx1
systemctl start nginx
cd /usr/share/nginx/html
chmod -R 777 /usr/share/nginx/html
rm index.html
wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/index.html
wget https://raw.githubusercontent.com/awsdevopsteam/route-53/master/ken.jpg
systemctl restart nginx
systemctl enable nginx

17. Review and launch the EC2 Instance

18. Once Instance is on, check if the Nginx Web Server is working from the web browser.