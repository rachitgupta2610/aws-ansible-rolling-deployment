# Ansible ELB Rolling  Deployment
Ansible playbook to roll a deploy of a java application running on tomcat, on hosts behind AWS ELBs.

### Introduction
This ansible playbook rolls updates to a set of application servers behind an Amazon load balancer (ELB).


#### steps :
##### pre-tasks: 
- As per Serial defined, no. of instances will be taken out for deployment.
- Remove the node(EC2-Instance) from the Elastic Load Balancer
##### deployment:
- Application (index.html) Deployment on the first instance. 
The application deployment is done through a tomcat-deployment role, which takes the following steps:
- Create a backup
- Stop tomcat
- Download the war file from an HTTP repository (in this case, locally)
- Startup tomcat
### Note:-
- Edit Serial as per reqiurement and no. of instances inder an ELB.
- Implement some sort of wait / app check, as when tomcat startups it ussually - - takes some time before the application is up and running
- User and password to get the application war should be optional
