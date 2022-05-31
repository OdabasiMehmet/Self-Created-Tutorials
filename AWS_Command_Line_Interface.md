# PART 1 INSTALLING AWS CLI for Windows

1. First check whether you have pre-installed aws on your system
```bash
aws --version
```
2. Download the msi windows installer from aws website

```bash
https://awscli.amazonaws.com/AWSCLIV2.msi
```
3. Install the program using default options.

# PART 2 CONFIGURING AWS CLI for Windows

1. Configure credentials for AWS

```bash
aws configure
```
2. Enter AWS Access Key ID

```bash
AWS Access Key ID [None]:
```
3. Enter AWS Secret Access Key

```bash
AWS Secret Access Key [None]:
```

4. Enter default region

```bash
Default region name [None]:
```
5. Enter default output

```bash
Default output format [None]:
```

# PART 3 INSTALLING AWS CLI ON EC2 

1. Check whether you have pre-installed aws on your system
```bash
aws --version
```
2. If you have Version 1 installed, you must uninstall it to install the version 2.

```bash
sudo yum remove awscli -y
```
3. Download aws cli by using curl command

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```
4. Unzip the file contents

```bash
unzip awscliv2.zip 
```
5. Install the cli
```bash
sudo ./aws/install
```