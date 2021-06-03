
# iac-deploy-tf-ansible 

Infrastructure as Code examples with [Terraform](https://www.terraform.io/) and [Ansible](https://www.ansible.com/) for AWS.

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