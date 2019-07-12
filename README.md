[arch]:images/arch.PNG

# CloudFormation Infrastructure as Code for a Web App

This project showcases how to build an network and server infrastructure to support a web application. The template comprises:

* VPC
* Internet Gateway and Attachment
* Private and Public Subnets
* Route Tables
* Route
* Subnet Route Table Associations
* Load Balancer and Web App Security Groups
* Load Balancer Listener and Rule
* Load Balancer Target Group
* Autoscaling Group
* Autoscaling App Launch Configuration

## Network Architecture

The architecture is shown below:

![arch]

## What it does

This CloudFormation template sets up the VPC shown above, installs Apache server and copies a webpage from Amazon S3 on autoscaled EC2 instances. The webpage/app is made available online as a high availability application that responds to amount of requests being made to the server.

## Running the template

* install and configure **AWS CLI**
* run
    > aws cloudformation create-stack --stack-name <your-stack-name> --template-body file://infra.yml --parameters file://infra.parameters.json --region=us-west-2 --capabilities CAPABILITY_IAM

## Outputs

Please note that the site might be removed by the time you are reading this

* DNS from AWS Load Balancer: **kb-ud-LoadB-1AP1P1O5Y9STY-1182758576.us-west-2.elb.amazonaws.com**
* Web address: http://kb-ud-LoadB-1AP1P1O5Y9STY-1182758576.us-west-2.elb.amazonaws.com/index.htm
