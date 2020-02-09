# This document is built to demonstrate full CI/CD flow on AWS using Opensource application 

Setup Jenkins Server on AWS
--
#### Install of Jenkins (CI/CD Pipelines) on Jenkins Server on AWS EC2 Linux instance (free tier)

	• Git Configuration (SCM Repo)
	• Maven Configuration (Build manager)
	• Configure SCM pull every minute 
	• Configure Github

Build WeAPP application  (Java 1.8 + Tomcat) 
--
#### Build WebApp using maven and push to GitHub Public repository  https://github.com

Setup Ansible Server & Docker Engine on AWS
--
#### Install of Ansible Server (Automation orchestration) on AWS EC2 Linux instance (free tier)

	• Install Docker Engine on Ansible Server
	• Docker Engine (Containerization) 
	• Pull built WebAPP from Github Public repository  https://hub.docker.com/
	• Create Docker image with WebApp over Tomcat  
	• Deploy Application on Docker & create Docker image
	• Push Docker image to Docker Hub (Public )

Setup Kubernetes (K8s) Cluster on AWS
--
#### Create Ubuntu Linux instance (free tier)  on AWS and install AWSCLI

	• Install  Kubernetes Server (Containers orchestration)   
	• Install Kube CTL 
	• Install KOPS  (Kubernetes Operations) to deploy Kubernetes Cluster
	• Create IAM role on AWS with full access to following services and attach role to Kubernetes Server 
		○ Route 53 (Create Private hosted Zone , Internal DNS )
		○ S3 Bucket (Storage )
		○ Elastic Load Balancer
		○ EC2 
	• Using KOPS Create Kubernetes Definitions  on S3 Bucket 
	• Create Kubernetes Cluster

Deploying WebApp pods on Kubernetes
--

#### On Ansible Server create Ansible Playbook to automate following tasks

	• Pull Docker image from Docker hub to Kubernetes Server
	• Deploy Web Application on 2 nodes replica set with Load balancer
	• Create Service & expose deployment as service to outside world  
	( This will create an ELB in front of those 2 containers and allow us to publicly access them)
		○ Validate Pods
		○ Validate Deployments
		○ Validate Service
		
	• Access WebApp application 
  
#### Make changes to WebApp and demo complete CI/CD flow

After demo
--
	• Destroy Deployment (kubectl)
	• Destroy Service (kubectl)
	• Delete Kubernetes Cluster (kops)
        
#### Shutdown AWS instances 
