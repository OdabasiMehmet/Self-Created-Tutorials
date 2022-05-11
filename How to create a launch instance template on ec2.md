## How to create an Instance with Launch Template and use Versioning

## Part 1 - Creating Launch Templates

### Step 1: Create Security Group

1. Create a Security Group to be used in Launch Template.

Allos SSH and HTTP with 22 and 80 ports by anywhere(0.0.0.0/0)

### STEP 2: Create Launch Template

2. Open the Amazon EC2 console 

3. On the navigation pane, under `INSTANCES`, choose `Launch Templates`.

4. Click on `Create launch template`. Keep most of the options default except the following

5. Enter a name and provide a description for the initial version of the launch template.


Name                         : Mytemplate
Template version description : Origin


6. For security groups choose the one with SSH and HTTP

7. Resource tags


Key             : Name
Value           : Webserver-Origin
Resource type   : Instance


### Step 3: Create an Instance with Launch Template

8. Go to `Launch Template` Menu

9. Select `MyTemplate` ---> `Actions` ---> `Launch Instance from Template`

10. Enter number of instance as `1`.

11. Keep the rest of settings as is and click the `Launch instance from template` at the bottom.

12. Go to EC2 Instance menu and show the created instance.

## Part 4 - Modifying Launch Template

### Step 1: Launch Template Version 2

1. Go to Launch Template menu on the left hand pane

2. Select template named `MyTemplate` ---> `Actions` ---> `Modify template (Create New Version)`

3. Template version description
V2 

4. Resource tags


Key             : Name
Value           : Webserver-V2
Resource type   : Instance


5. Go to `Advance Details` on the bottom and add the script given below into the `user data` field.

#!/bin/bash

yum update -y
amazon-linux-extras install nginx1
systemctl enable nginx
systemctl start nginx

6. Go to `Launch Template` Menu and click on `MyTemplate`.

7. Select version `2` from the `Versions` tab.

Version         : 2
Description     : V2 

30. Select `Actions` ---> `Launch instance from template`.

Number of Instance : 1

31. Click the 'launch Instance from template' button at the bottom.

32. Go to `Instance Menu` and show recently created EC2 instance.

33. Copy EC2's 'Public IP`, paste it in a browser and show 'nginx' webpage.

### Step 2: Launch Template Version 3

1. Go to `Launch Template` menu on the left hand pane.

2. Select template named `MyClaruswayTemplate` ---> `Actions` ---> 'Modify template (Create New Version)'.

3. Template version description


V3 

4. Resource tags


Key             : Name
Value           : Webserver-V3
Resource type   : Instance


5. Go to `Advance Details` on the bottom and add the script given below into the `user data` field.


#! /bin/bash

yum update -y
amazon-linux-extras install nginx1
systemctl start nginx
cd /usr/share/nginx/html
chmod -R 777 /usr/share/nginx/html
rm index.html
wget https://raw.githubusercontent.com/awsdevopsteam/ngniex/master/index.html
wget https://raw.githubusercontent.com/awsdevopsteam/ngniex/master/ryu.jpg
systemctl restart nginx
systemctl enable nginx


6. Go to `Launch Template` Menu and click on `MyTemplate`.

7. Select version `3` from the `Versions` tab.


Version         : 3
Description     : V3 


8. Select `Actions` ---> `Launch instance from template`.


Number of Instance : 1

9. Click the `launch Instance from template` button at the bottom.

10. Go to `Instance Menu` and show recently created EC2 instance.

11. Copy EC2's `Public IP`, paste it in a browser and show `nginx` webpage with custom image.