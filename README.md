# BHSNEW

Terraform downloaded via these commands
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt-get update && sudo apt-get install terraform

#Commands to execute
terraform init
terraform plan -out main.tfplan
terraform apply main.tfplan

#To validate
terraform output -raw tls_private_key > id_rsa
terraform output public_ip_address
ssh -i id_rsa azureuser@<public_ip_address>


#Results as this :
#New instance created via terraform :

public_ip_address = "13.82.47.157"
resource_group_name = "TestBHS_rsc-relieved-newt"
