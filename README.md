
 
# Terraform AWS VPC Module 

This Terraform configuration sets up an AWS Virtual Private Cloud (VPC) with public and private subnets. It utilizes a module to manage VPC resources across different environments. 

## Files  
 
- **main.tf**: Defines the AWS provider and resources for creating the VPC and subnets. 
- **variables.tf**: Defines input variables used in the configuration. 
- **dev-vpc.tf**: Configuration for the development environment using the `tf-vpc` module. 
- **prod-vpc.tf**: Configuration for the production environment using the `tf-vpc` module.
- **outputs.tf**: Defines output values to be displayed after Terraform applies the configuration.

## Usage

1. **Set up AWS Provider**: Ensure you have AWS credentials configured either through environment variables or AWS CLI configuration.

2. **Adjust Variables (if necessary)**: Modify `variables.tf` to customize CIDR blocks or other parameters as needed.

3. **Initialize Terraform**: Run `terraform init` in the directory where these files are located to initialize Terraform and download necessary providers.

4. **Review Plan**: Run `terraform plan` to see the execution plan and ensure it matches your expectations.

5. **Apply Changes**: Run `terraform apply` to apply the configuration and create the AWS resources.

6. **Destroy Resources**: If needed, run `terraform destroy` to destroy the created AWS resources.

## Modules

- **tf-vpc**: A module located in the `../modules` directory is used to encapsulate the VPC creation logic. It accepts an `environment` parameter to distinguish between environments (DEV, PROD).

## Outputs

- **vpc-cidr-block**: Outputs the CIDR block of the VPC created by the `tf-vpc` module.

## Notes

- Ensure proper AWS IAM permissions are set for the AWS credentials used with Terraform.
- This configuration assumes AWS region `us-east-1`. Modify `provider "aws"` block in `main.tf` to change the region if necessary.
