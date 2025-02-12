# cea_cloudformation

This file will be used to track down notes of what I've completed on what day for my AWS CloudFormation project. The goal is to configure and deploy AWS CloudFormation code. 


** Feb 11, 2025: 

I created a s3-bucket.yaml & vpc.yaml file. 

In the s3-bucket.yaml file, I added code to create a new S3 bucket labelled "nik-s3-bucket-yaml" and pushed this to my AWS console via AWS CLI. 

In the vpc.yaml file, I added code to create a VPC, 6 subnets (2 public 4 private, 2 AZ), internet gateway, and public route table. This code was pushed to my AWS console via AWS CLI. 

When pushing the code in vpc.yaml to the AWS console, there were some code errors I ran into that I fixed. I then updated the vpc using update-stack in the AWS CLI.  