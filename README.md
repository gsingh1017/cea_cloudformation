# cea_cloudformation

This file will be used to track down notes of what I've completed on what day for my AWS CloudFormation project. The goal is to configure and deploy AWS CloudFormation code. 


** Feb 11, 2025: 

I created a s3-bucket.yaml & vpc.yaml file. 

In the s3-bucket.yaml file, I added code to create a new S3 bucket labelled "nik-s3-bucket-yaml" and pushed this to my AWS console via AWS CLI. 

In the vpc.yaml file, I added code to create a VPC, 6 subnets (2 public 4 private, 2 AZ), internet gateway, and public route table. This code was pushed to my AWS console via AWS CLI. 

When pushing the code in vpc.yaml to the AWS console, there were some code errors I ran into that I fixed. I then updated the vpc using update-stack in the AWS CLI.  


** Feb 12, 2025: 

Added bastion instance & security group in vpc.yaml. 

Added app private instance and security group for AZ 1 & 2. 

Pushed update to AWS Cloudformation via AWS ClI. 

In AWS CLI, SSH into bastion, then SSH into App1 instnce. Ping App2 instance from App1. 


** Feb 15, 2025

Added iam.yaml file. This file contains a test IAM AWS CloudFormation stack. This is the very first IAM stack I created.


** Feb 16, 2025

Found error in vpc.yaml where i was adding all 6 subnets into one AZ. Changed this so there are 3 subnets in each AZ. 

Created ec2.yaml file. This file contains the same vpc, subnets, igw, and public route tables from vpc.yaml. I added a two public web server instances each in a seperate AZ, a web server security group, an application load balancer (ALB), listener for ALB, and a target groups for ALB. 

Created asg.yaml file. This file contains same vpc from vpc.yaml and WebServerSecurityGroup from ec2.yaml. I added an auto-scaling launch configuration, auto scaling group, cloudwatch high CPU alarm, and a scaling out policy. 

All deployed stacks have worked as expected. 


** Feb 17, 2025

Created s3-static.yaml file and index.html file. The s3-static.yaml file creates an S3 stack with a policy that allows public to view the object. The object is the index.html file which was copied from AWS CLI to s3 bucket. 

Created rds.yaml file. This file creates a MySQL RDS. It took cloudformtion almost 40 minutes to create this stack. 