# Terraform_withcontainer
Infrastructure Provisioning and app deployement in ECS
Create a repo in aws ECR name - > django-app

IMPORTANT - Once the repo is create change the 011847968431.dkr.ecr.us-west-1.amazonaws.com BELOW VALUES IN COMMANDS TO THE REPO OF YOURS


aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 011847968431.dkr.ecr.us-west-1.amazonaws.com


cd app/


docker build -t 011847968431.dkr.ecr.us-west-1.amazonaws.com/django-app:latest . 


docker push 011847968431.dkr.ecr.us-west-1.amazonaws.com/django-app:latest

Change the docker_image_url_django in VARIABLES.TF file with your current repo name 


Change the file paths in iam.tf and variables.tf file

Go to terraform folder and hit this below command 

ssh-keygen -f california-region-key-pair


terraform init 


terraform plan -out terraform.out


terraform apply "terraform.out"
