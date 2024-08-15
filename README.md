## Description
This is a demo project for provisioning Nginx Webserver on AWS EC2 using Terraform. In this demo, we are provisioning a Nginx instance on AWS EC2 using user data. We also setup a security group with the necessary rules.

## Usage
- Execute the command `terraform init` to setup the project workspace.
- Execute the command `terraform apply` to provision the infrastructure. This will create a VPC with Private and Public Subnets, a NAT Gateway and three EC2 instances.
- Execute the command `terraform destroy` to destroy the infrastructure.

## Note
The resources created in this example may incur cost. So please take care to destroy the infrastructure if you don't need it.