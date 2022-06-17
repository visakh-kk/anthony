# classic-apparels

Creates the following AWS resources:

* Custom VPC, private and public subnets.
* EC2 instances
* Key pair.
* Backup plan.
* Custom security groups.
* SSM role for EC2.

## Pre-requirements

* Setting the environment variable changes the value used until the end of your shell session, or until you set the variable to a different value.

```
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_DEFAULT_REGION=""
aws sts get-caller-identity  --> (To confirm the identity of the user)
```

## Usage

* Use "terraform.tfvars" file to edit variables.

```hcl
region               = "eu-west-1"
vpc_name             = "CFAI-VPC"
vpc_cidr             = "10.60.0.0/20"
azs                  = ["eu-west-1a", "eu-west-1b"]
public_subnets_cidr  = ["10.60.0.0/24", "10.60.1.0/24"]
private_subnets_cidr = ["10.60.2.0/24", "10.60.3.0/24"]


```
### Run terraform module
```
terraform init
terraform plan 
terraform apply 
```
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->


## Outputs

| Name | Description |
|------|-------------|
| VPC\_id | The ID of the VPC |
| VPC\_CIDR\_Block | The CIDR of the VPC |
| Private\_subnets\_id | List of IDs of private subnets |
| Public\_subnets\_id | List of IDs of public subnets |
| NAT\_IP | List of public Elastic IPs created for AWS NAT Gateway |
| Availability\_Zones |List of availability zones specified as argument to this module |
| trendz_cmp_app_IP | The IP of the Trendz CMP App Server. |
| trendz_cmp_sql_IP | The IP of the Trendz CMP SQL Server. |
| trendz_cmp_sql_IP | The IP of the Trendz CMP Report Server. |
| key\_pair | The name of Key_pair  |


<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
