1.Update config.yaml 2.Update secrets.yaml [Optional] 3.Update params.yaml 4.Update the entity 5.Update the configuration manager in src config 6.Update the components 7.Update the pipeline 8.Update the main.py 9.Update the dvc.yaml

AWS-CICD-Deployment-with-Github-Actions

Login to AWS console.
Create IAM user for deployment
with specific access
EC2 access : It is virtual machine

ECR: Elastic Container registry to save your docker image in aws

Description: About the deployment
Build docker image of the source code

Push your docker image to ECR

Launch Your EC2

Pull Your image from ECR in EC2

Lauch your docker image in EC2

Policy:
AmazonEC2ContainerRegistryFullAccess

AmazonEC2FullAccess

Create ECR repo to store/ave docker image
- Save the URI: 509399594359.dkr.ecr.eu-north-1.amazonaws.com/chicken
Create EC2 machine (Ubuntu)

Open EC2 and Install docker in EC2 Machine:

optinal
sudo apt-get update -y

sudo apt-get upgrade

required
curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker

Configure EC2 as self-hosted runner:
setting>actions>runner>new self hosted runner> choose os> then run command one by one

Setup github secrets:
AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = us-north-1

AWS_ECR_LOGIN_URI = demo>>

ECR_REPOSITORY_NAME = simple-app