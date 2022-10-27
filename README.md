# terraform-aws-vpc-endpoint

# main.tf

```
module "vpc_endpoint_main" { 
	source               		 = "git::https://github.com/tothenew/terraform-aws-vpc-endpoint.git"
	protocol			 = var.protocol
	to_port				 = var.to_port
	from_port			 = var.from_port
	vpc_id 				 = var.vpc_id
	sg_description		 	 = var.sg_description
	region				 = var.region
	subnet_ids			 = var.subnet_ids
	common_tags			 = var.common_tags
	route_table_ids		 	 = var.route_table_ids
	project_name_prefix	 	 = var.project_name_prefix
	profile				 = var.profile
}
```


# terraform.tfvars

```
region               = "ap-south-1"
profile              = ""
project_name_prefix  = "tothenew"

common_tags 	     = {
    	   "Feature" : "application"
}

project              = "ToTheNew"
environment 	     = "dev"
subnet_ids 	     = [""]
vpc_id 		     = ""
route_table_ids      = [""]
from_port 	     = 443
to_port 	     = 443
protocol 	     = "tcp"
sg_description	     = "Security group created for VPC endpoint"
```

# output.tf

```
output "vpc_endpoint_sg_id" {
  value = module.security_group.vpc_endpoint_sg_id
}

output "ssm_interface_id" {
	value = module.ssm_interface.vpc_endpoint_id
}
output "ssm_interface_arn" {
	value = module.ssm_interface.vpc_endpoint_arn
}

output "ssm_messages_interface_id" {
	value = module.ssm_messages_interface.vpc_endpoint_id
}
output "ssm_messages_interface_arn" {
	value = module.ssm_messages_interface.vpc_endpoint_arn
}

output "ec2_messages_interface_id" {
	value = module.ec2_messages_interface.vpc_endpoint_id
}
output "ec2_messages_interface_arn" {
	value = module.ec2_messages_interface.vpc_endpoint_arn
}

output "s3_gateway_id" {
	value = module.s3_gateway.vpc_endpoint_id
}
output "s3_gateway_arn" {
	value = module.s3_gateway.vpc_endpoint_arn
}

output "cloudwatch_logs_interface_id" {
	value = module.cloudwatch_logs_interface.vpc_endpoint_id
}
output "cloudwatch_logs_interface_arn" {
	value = module.cloudwatch_logs_interface.vpc_endpoint_arn
}

output "cloudwatch_monitoring_interface_id" {
	value = module.cloudwatch_monitoring_interface.vpc_endpoint_id
}
output "cloudwatch_monitoring_interface_arn" {
	value = module.cloudwatch_monitoring_interface.vpc_endpoint_arn
}

output "ec2_interface_id" {
	value = module.ec2_interface.vpc_endpoint_id
}
output "ec2_interface_arn" {
	value = module.ec2_interface.vpc_endpoint_arn
}

output "ecr_api_interface_id" {
	value = module.ecr_api_interface.vpc_endpoint_id
}
output "ecr_api_interface_arn" {
	value = module.ecr_api_interface.vpc_endpoint_arn
}

output "ecr_dkr_interface_id" {
	value = module.ecr_dkr_interface.vpc_endpoint_id
}
output "ecr_dkr_interface_arn" {
	value = module.ecr_dkr_interface.vpc_endpoint_arn
}

output "autoscaling_interface_id" {
	value = module.autoscaling_interface.vpc_endpoint_id
}
output "autoscaling_interface_arn" {
	value = module.autoscaling_interface.vpc_endpoint_arn
}

output "elb_interface_id" {
	value = module.elb_interface.vpc_endpoint_id
}
output "elb_interface_arn" {
	value = module.elb_interface.vpc_endpoint_arn
}

output "sns_interface_id" {
	value = module.sns_interface.vpc_endpoint_id
}
output "sns_interface_arn" {
	value = module.sns_interface.vpc_endpoint_arn
}

output "sqs_interface_id" {
	value = module.sqs_interface.vpc_endpoint_id
}
output "sqs_interface_arn" {
	value = module.sqs_interface.vpc_endpoint_arn
}

output "secrets_manager_interface_id" {
	value = module.secrets_manager_interface.vpc_endpoint_id
}
output "secrets_manager_interface_arn" {
	value = module.secrets_manager_interface.vpc_endpoint_arn
}

output "lambda_interface_id" {
	value = module.lambda_interface.vpc_endpoint_id
}
output "lambda_interface_arn" {
	value = module.lambda_interface.vpc_endpoint_arn
}

output "cloudwatch_monitoring_interface_id" {
	value = module.cloudwatch_monitoring_interface.vpc_endpoint_id
}
output "cloudwatch_monitoring_interface_arn" {
	value = module.cloudwatch_monitoring_interface.vpc_endpoint_arn
}

output "dynamodb_gateway_id" {
	value = module.dynamodb_gateway.vpc_endpoint_id
}
output "dynamodb_gateway_arn" {
	value = module.dynamodb_gateway.vpc_endpoint_arn
}
```
