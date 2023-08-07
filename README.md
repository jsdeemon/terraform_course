## Terraform course 
https://www.youtube.com/watch?v=l5k1ai_GBDE 

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




- Terraform Architecture and commands 

- Example Configuration File 

