# rockstar-terraform-eks

## Introduction

* This is a Rockstar react application
* AWS EKS cluster is created using terraform 
* Deployment is created on EKS cluster with the dockerized rocker app


### Prerequisites

* Node.js
* AWS CLI
* Docker
* terraform

### Setup

* Clone the repo from here -> https://github.com/sdileepkumarreddy/rockstar-terraform-eks.git

### How to Run??

* Navigate to downloaded tf-code and execute `terraform init` , `terraform plan` and `terraform apply` and new EKS cluster with the name terraform-eks-demo will be created
* Update kubeconfig by executing command `aws eks update-kubeconfig --name terraform-eks-demo --region us-west-2`
* Copy the output of `terraform output config_map_aws_auth` to a config-map-aws-auth.yml file and execute `kubectl apply -f ./config-map-aws-auth.yml` for accessing nodes.
* Apply service and deployment by executing `kubectl apply -f service.yml` and `kubectl apply -f deployment.yml`
* Application can be accessed with Loadbalancer URL that can be found by `kubectl get svc`


