### Code for variable.tf
variable "region" {
    description = "the region where the infra will be created"
    type = string
    default = "ap-south-1"
}

variable "access_key" {
    description = "the access key of the aws account"
    type = string 
    default = "AKIAT3ARS5FLKKGSGUU5"
}

variable "secret_key" {
    description = "the access key of the aws account"
    type = string 
    default = "8TAaZ2z1IXeD4BAzRM01r7Jmzpxw/Q9wG2SD4vxP"
}

variable "s3_bucket_name" {
    type = string
    default = "pankaj-tf-testing"
}

variable "instance_type" {
    description = "the instance type of ec2"
    type = string
    default = "t2.micro"
}

variable "ami" {
    description = "the image to use for creating ec2 instance"
    type = string
    default = "ami-0c1a7f89451184c8b"
}
