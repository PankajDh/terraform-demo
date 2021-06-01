# Infastructure as Code - Terraform
***

We will be creating some basic AWS infra to learn basic terraform
Follow all the steps and if you have any doubt you can reach out to Pankaj, Ayush, Himanshu or Aman

### Prerequisites

1. Install terraform from https://learn.hashicorp.com/tutorials/terraform/install-cli
2. Create an AWS free tier account

### Get Started

#### Get AWS Credentials
1. Login to your AWS console
2. Click on your name on the right top corner and then click `My Security Credentails`
3. Copy access key id and create access key


#### File Structure
1. Create three files main.tf, variable.tf and output.tf in the root
2. Main.tf will have all the logic, variable.tf will have all the variable details and output.tf will be used for returns
3. Terraform concats all the files before running

#### Now Let's Code
1. Tell terafrom where to create the infra 
```
provider "aws" {
  region = var.region
  access_key = var.access_key
  secret_key = var.secret_key
}
```
2. Create ec2 instance 
```
resource "aws_instance" "my_server" {
  ami           = var.ami
  instance_type = var.instance_type
}
```
3. Create s3 bucket
```
resource "aws_s3_bucket" "terraform_state" {
  bucket = var.s3_bucket_name

  # enabling versioning so that we can revert back anytime easily
  versioning {
    enabled = var.enable_versioning
  }
}
```
4. Run `terraform init`
5. Run `terraform fmt`. This command formats your code
6. Run `terraform validate`
7. Run `terraform plan`
8. Run `terraform apply`
9. *Modules* 
