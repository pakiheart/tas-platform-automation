Create s3 bucket for state file - tfstate-tas

cd terraform/aws
terraform init -backend-config="access_key=$TF_VAR_access_key" \
  -backend-config="secret_key=$TF_VAR_secret_key" \
  -backend-config="bucket=tfstate-tas" \
  -reconfigure -upgrade

terraform plan -var-file=../../secrets/terraform.tfvars

terraform apply -var-file=../../secrets/terraform.tfvars