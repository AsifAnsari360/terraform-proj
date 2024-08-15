## Description
This is a demo project for provisioning Nginx Webserver on AWS EC2 using Terraform. In this demo, we are provisioning a Nginx instance on AWS EC2 using user data. We also setup a security group with the necessary rules.

## Perquisite
- First, create an IAM (Identity and Access Management) user in AWS, [follow these steps.](https://github.com/AsifAnsari360/terraform-proj/blob/main/IAM-USER/README.md)
- Important: Don't forget to save Access Key ID and Secret Access Key, as we will be needing it further.
- We will be running this project on AWS using an EC2 instance.
  - First of all setup an EC2 instance machine on AWS and after that install Terraform to get started with the project. The commands to install Terraform are provided below.
## Installation Terraform and AWS-CLI
#### Ubuntu/Debian

- Ensure that your system is up to date and you have installed the gnupg, software-properties-common, and curl packages installed. You will use these packages to verify HashiCorp's GPG signature and install HashiCorp's Debian package repository.
```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```
- Install the HashiCorp GPG key.
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```
- Verify the key's fingerprint.
```bash
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```
- Add the official HashiCorp repository to your system. The lsb_release -cs command finds the distribution release codename for your current system, such as buster, groovy, or sid.
```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```
- Download the package information from HashiCorp.
```bash
sudo apt update
```
- Install Terraform from the new repository.
```bash
sudo apt-get install terraform
```
- To verify if Terraform is installed.
```bash
sudo terraform --version
```

#### AWS-CLI

- To install aws-cli RUN the following command.
```bash
sudo snap install aws-cli --classic
```

## **# Setup**

- To get this repository, run the following command inside your git-enabled terminal
```bash
https://github.com/AsifAnsari360/terraform-proj.git
```
- Before moving forward there are some changes you need to do in main.tf and variable.tf files.
- In main.tf file, 
```bash
provider "aws" {
    region = "ap-south-1"       # Add your region name
    profile = "terraform-user"  # Add the IAM username that you created 
}
```
- In variable.tf file,
```bash
variable "key_name" {
    description = "Key to access the EC2 instance"
    type = string
    default = "data-key"                     # Add the key pair you created
}
```
You can also use the key pair that you are currently using for the EC2 instance running. 

- Now RUN the following command to add Access Key ID, Secret Access Key and region.
```bash
aws configure --profile terraform-user
```
Leave the Default output format blank, and press Enter.

## Usage
- Execute the command `terraform init` to setup the project workspace.
```bash
terraform init
```
- Execute the command `terraform apply` to provision the infrastructure. This will create a VPC with Private and Public Subnets, a NAT Gateway and three EC2 instances.
```bash
terraform apply
```
- Execute the command `terraform destroy` to destroy the infrastructure.
```bash
terraform destroy
```
## Note
The resources created in this example may incur cost. So please take care to destroy the infrastructure if you don't need it.
