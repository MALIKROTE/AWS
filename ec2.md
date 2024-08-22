# EC2

### Steps to create EC2 using UI
    1.Log in to aws console
    2.search for instance service
    3.select ec2
    4.click on launch ec2
    5.provide ec2 name or tag
    6.select application and os image
    7.then select AMI
    8.then select architecture
    9.then select instance type ex. t2.micro... etc
    10.selct key pair
    11.network setting setup security group, allow ssh traffic
    12.configure storage
    13.advanced settings
    14.Click on the launch instance it will create a new instance
    
### Using terraform
    terraform {
        required_providers {
            aws = {
                source  = "hashicorp/aws"
                version = "~> 5.0"
            }
        }
    }
    provider "aws" {
        region = "ap-south-1" *//select region as per your requirement*
  
    }
    resource "aws_instance" "malik" { *// you can change resource name as well //*

        ami = "ami-0ad21ae1d0696ad58" *//select ami as per your requirement also using variable, runtime and using multiple ways to get it//*
        instance_type = "t2.micro" *//this is instance type of ec2//*
    }

**Apart from this we can add security groups if needed specifically. Also we can add key pair as well, tags also added to the security groups.**