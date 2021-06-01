
# iac-deploy-tf-ansible 

Infrastructure as Code examples with [Terraform](https://www.terraform.io/) and [Ansible](https://www.ansible.com/)


# Persisting Terraform State in S3 Back End
Example of how save the Terraform state file in S3 bucket

### Create S3 bucket 

First we need to create a S3 bucket file:

    aws s3api create-bucket --bucket <BUCKET_NAME>

Then we need to initialize the backend with the following command:

    terraform init
