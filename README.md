
# iac-deploy-tf-ansible 

Infrastructure as Code examples with [Terraform](https://www.terraform.io/) and [Ansible](https://www.ansible.com/) for AWS.

### Table of contents:

  - [Persisting Terraform State in S3 Back End](#persisting-terraform-state-in-s3-back-end)
    - [Create S3 bucket](#create-s3-bucket)
    - [Init the backend](#init-the-backend)
  - [Using variables and providers](#using-variables-and-providers)
  - [Deploying VPCs, Internet GWs, and Subnets](#deploying-vpcs-internet-gws-and-subnets)
  - [Deploying Multi-Region VPC Peering](#deploying-multi-region-vpc-peering)
  - [Deploying Security groups](#deploying-security-groups)
  - [Using Data Source (SSM Parameter Store) to Fetch AMI IDs](#using-data-source-ssm-parameter-store-to-fetch-ami-ids)
  - [Deploying Key Pairs for App Nodes](#deploying-key-pairs-for-app-nodes)
  - [Create EC2 instances](#create-ec2-instances)
  - [Destroy Terraform objects](#destroy-terraform-objects)

## Persisting Terraform State in S3 Back End
Example of how save the Terraform state file in S3 bucket. Changes on the backend can be found on the [backend.tf](backend.tf) file
### Create S3 bucket 

First we need to create a S3 bucket file:

    aws s3api create-bucket --bucket <BUCKET_NAME>

### Init the backend 
Then we need to initialize the backend with the following command:

    terraform init

## Using variables and providers

Example of how to use variables and providers in Terraform can be found in: [variables.tf](variables.tf) and [providers.tf](providers.tf)

## Deploying VPCs, Internet GWs, and Subnets

Example of how to deploy in Terraform AWS VPCs, Internet GWs, and Subnets can be found in: [networks.tf](networks.tf) 
## Deploying Multi-Region VPC Peering

Example of how to deploy in Terraform Multi-Region VPC peerings can be found in: [networks.tf](networks.tf) 

## Deploying Security groups

Example of how to deploy Security Groups in Terraform can be found in [security_groups.tf](security_groups.tf) 


## Using Data Source (SSM Parameter Store) to Fetch AMI IDs

Example of how to use Data source to fetch AMI ids can be found in [instances.tf](instances.tf) 


## Deploying Key Pairs for App Nodes
   
To create the authentication key pairs for SSH use the following command:

    ssh-keygen -t rsa

A public and a private key will be created in your `~/.ssh` directory

The example of how to atach the key pairs in the EC2 instances can be found in: [instances.tf](instances.tf)

## Create EC2 instances

Example of how to create the EC2 instances can be found in: [instances.tf](instances.tf)

A example of how to get the ips of the created instances can be found: [outputs.tf](outputs.tf)


## Destroy Terraform objects

If you are testing and want a destroy all remote objects managed by this Terraform configuration use:

    terraform destroy
