# Apache Web Server Deployment using CloudFormation

## Project Overview
This project involves deploying an Apache web server on an Amazon Linux 2023 EC2 instance using AWS CloudFormation. The stack references a pre-existing network stack and outputs the private IP address and public DNS name of the EC2 instance.

## Prerequisites
- An existing VPC stack (SampleNetworkCrossStack)
- AWS CLI configured
- A valid EC2 Key Pair

## Stack Deployment
1. Deploy the Sample Network Stack:
    ```sh
    aws cloudformation create-stack --stack-name SampleNetworkStack --template-body file://sample-network-stack.yaml --region us-west-2
    ```
2. Deploy the Apache EC2 Instance Stack:
    ```sh
    aws cloudformation create-stack --stack-name ApacheEC2Stack --template-body file://apache-ec2-template.yaml --parameters ParameterKey=InstanceType,ParameterValue=t2.micro ParameterKey=KeyName,ParameterValue=your-key-name ParameterKey=VpcStackName,ParameterValue=SampleNetworkStack --region us-west-2
    ```

## Accessing the Apache Server
- SSH into the EC2 instance using:
    ```sh
    ssh -i your-key-name.pem ec2-user@<ElasticIP>
    ```
- Open a web browser and navigate to `http://<ElasticIP>` to see the Apache web page.

## Repository Contents
- `sample-network-stack.yaml`: CloudFormation template for the network stack.
- `apache-ec2-template.yaml`: CloudFormation template for the Apache EC2 instance.
- Screenshots of the deployed Apache web page.

## License
This project is licensed under the @christian@ License.
