## Terraform course 
https://www.youtube.com/watch?v=l5k1ai_GBDE 

How to use Terraform with docker-compose 
https://londonappdeveloper.com/how-to-use-terraform-via-docker-compose-for-professional-developers/

### With Jenkins
https://spacelift.io/blog/terraform-jenkins
- Step 1: Installing Terraform Plugin on Jenkins. ...
- Step 2: Installing Terraform Binary. ...
- Step 3: Preparing the Terraform Config. ...
- Step 4: Create a Jenkins Pipeline. ...
- Step 5: Jenkins Pipeline Script. ...
- Step 6: Configuring Access to AWS. ...
- Step 7: Testing the Pipeline.


- What is Terraform? 

Terraform allows to automate and nanage your infrastructure
your platform and services that run on that platform

It is open source and uses Declarative language - define WHAT and result you want 

Imperative style - define exact steps - HOW 

Terraform is a tool for infrastructure provisioning 

You have an application -> my-app

You developed infrastructure for application 

- several servers, where you deploy 5 microservice that make up your application as Docker containers and also you deploy a database container
+ AWS 
- prepare infrastructure
   -- private network space
   -- ec2 server instances
   -- install docker and other tools inside each one
   -- setup security on your servers )firewalls, etc.)_


### 2 Stages
- 1. Provisioning infrastructure - DevOps
- 2. Deploying application - Software Developers

Terraform is used on the 1 stage where Provisioning infrastructure:
- create VPS
- create AWS users and permissions
- spin up servers
- install Docker 

- What is Terraform used for?

- Difference between Terraform and Ansible:
they are both Infrastructure as a Code
both used to automate provisioning, configuring and managing the infrastructure

Terraform is mainly infrastructure provisioning tool
Ansible is mainly configuration tool - to configure that infrastructure 
Ansible is more mature, and Terraform is new
Terraform is much more advanced in Orchestration 
Terraform better for infrastructure 
Ansible better for configuring infrastructure

DevOps engineers use a combination of Terraform and Ansible for own strings 



Managing existing infrastructure
- create inftraatructure
- managing the infrastructure
  -- automate the continouse changing to your infrastructure
- replicating infrastructure 

Dev environment -> prod environment -> create same infrastructure for production 

how does Terraform connect to infrasttucture?

- Terraform Architecture and commands 

Terraform has 2 main components:
- Core. Core has 2 input sources:
1. Terraform configuration that you as a user write and where you define what needs to be created or provisioned 
2. State - makes state how infrastructure looks like 

Core takes this two inputs and makes a plan: what needs to be created/updated/destroyed 
It compares current state with a desired state (config file)

- Providers - AWS, Azure, IAAS

Terraform has a providers for other such Kubernetes
Enables to create and deploy K8s on top of it and create a services and components inside that k8s cluster  

Terraform has over 100 providers for different technologies 

With k8s Provider you can have access to different K8s resources 

Executes the plan with providers 

### Example Configuration File 
```bash
provider "kubernetes" {
  config_path    = "~/.kube/config"
  config_context = "my-context"
}

resource "kubernetes_namespace" "example" {
  metadata {
    name = "my-first-namespace"
  }
}


# create a VPC

resource "aws_vpc" "example" {
    cidr_block = "10.0.0.0/16"
}
```

```bash
provider "aws" {
  region                  = "your region"
  shared_credentials_file = "path_file_credentials like C:\Users\terraform\.aws\credentials"
  profile                 = "profile_name"
}


provider "aws" {
  region     = "us-west-2"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
}
```

Imperative defines HOW it is shoud be

What does declarative mean exactly? 

You define the end-state in your config file

For example, i want:
- 5 xervers with following network config
- AWS user with permissions i define in config


Benefits with updating the infrastructure:

Imperative config file:
- remove 2 servers
- add firewall config

YOU GIVE INSTRUCTIONS


BUT IN DECLARATIVE APPROACH IN TERRAFORM
you configure desired state 

so Terraform checks current state with your new desired state from config file and makes all your wishes

DECLARATIVE config file:
- 7 servers
- this firewall config
- user with following permissions 

adjust old config and ere-executes 


### Terraform commands
- refresh 

with refresh command query the infrastructure provider to get current state 

- plan

determines what actions are necessary to achieve the desired state 

- apply 

executes the plan 

-destroy

destroy the resources/infrastructure -one by one 



