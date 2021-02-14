# PROJECT-HYBRID-CLOUD-SAAS-THREE-TIER-WEB-APPLICATION
Third Project of Udacity and Nutanix Hybrid Cloud Engineer Nanodegree Program

## Project Overview

What are you going to build?
After your success making the software developers productive on the private cloud with the "Private Cloud SaaS: Three-Tier Web Application" project, you are now tasked with
extending the model of the E-Commerce Company’s basic web application to a hybrid cloud deployment, in order to maximize high availability and scalable performance. In addition, 
you are tasked with creating small and medium deployment scenarios.

## Project Steps

In order to complete the project, you will need to be able to:

* Design a blueprint to deploy and configure a three tier web application with a load balancer hosted on the private cloud, two web server tiers (each hosted on a private and a 
public cloud), and database VM hosted on the public cloud.
* Insure each VM in configured with the proper resources and tasks
* Test the deployment works with a read and write to the database.
* Test web tier scaling: scale-in and scale-out actions changing the population by a count of 1 on private cloud separately from scaling on the public cloud.
* Allow self-service, ad-hoc backup of the database.
* Create two application profiles for deployment for a small (1 vCPU, 1 core, 1GB RAM or t2.micro) and medium (2vCPU, 2 cores, 1GB RAM or t2.micro) CPU and memory configuration 
variants.

## Project Requirements

After speaking to management in the software engineering release, you learn the business requirements are to provide a pilot self-service, three tier web application using The
E-Commerce Company’s standards. In order to provide business continuity and performance scalability past the Course 2 Project, multiple infrastructure providers are required for
the web tier. The requirements have grown to incorporate a hybrid deployment model using private and public cloud, additional SaaS-like functionality for database backup and 
restoral, as well deployment resource size choices to help the developers become self-sufficient for different development and test workloads and common IT requests.

## The three tiers of the web application are:

* a load balancer,
* a web server,
* and a database server.

Developers need two sizes of deployment scenarios (small and medium), the ability to scale in and scale out the web tier independently on each provider, and to perform a 
database backup and restoral at any time.

* 1. The IT Manager states that all private cloud VMs must:
* Use the CentOS 8 cloud image for private cloud VMs located in the CentOS image repository (currently CentOS-8-GenericCloud-8.2.2004-20200611.2.x86_64.qcow2)
* For public cloud VMs, use the AWS Linux free tier option in your region, which currently in us-west-2 is
"Red Hat Enterprise Linux 8 (HVM), SSD Volume Type - ami-02f147dfb8be58a10 (64-bit x86)"
* Create and use the teccadmin account to configure the OS and install software.
* All VM accounts require using SSH access and can be granted sudo privileges.

* 2. The IT manager has already worked with the Software Release and Database Administration manager and negotiated the following developer requirements for the application 
environment:
* The load balancer VM will be a monolith for this project and use the latest HAProxy software included with the OS
* The load balancer will be hosted on the private cloud
* The web tier will use Apache web server and use the latest version of httpd software included with the OS
* For the hybrid cloud: there should be a web tier hosted on the private cloud and the public cloud
* The web tier VMs should be named wwwX, where X is a number. E.g: www0, www1, www2, etc.

* There will be two deployment scenarios, name each as follows and use the same VM resource sizes for all services:
## Small:
* 1 vCPU, 1 core, 1GB RAM on private cloud
* t2.micro on AWS public cloud
* Web tier VM starts at 1 replica and can scale to a maximum of 2, all others services cannot scale.

## Medium:
* 2vCPUs, 2 cores, 1GB RAM on private cloud
* t2.micro on AWS public cloud
* Web tier VM starts at 2 replicas and can scale to a maximum of 4, all others services cannot scale.

* No VM resource parameters can be changed by the end user
* The developer should be able to manually scale the either provider’s web tier independently in and out by one VM at a time and the load balancer must use the updated hybrid
web tier population
* After deployment, a developer can perform a database backup or a database restoral operation at any time

* 3. The Database Administrator manager states that all database VMs must:
* The database VM will be a monolith for this project and use MySQL, latest version 8.x software
* Create and use the teccdba account to configure the database password and structure
* Alter the root database account password to a user provided password at launch
* The test web application database should be named webapp and the table should be named tecc_dba_test and a user account tecc_webuser should be granted access to the database
and
share the root password
* The database will be hosted on the public cloud and should allow database access from the public and private cloud web tier hosts

* 4. The Software Release manager requires the environment to pass a test to ensure the configuration works for a developer:
* The web app should be installed to the standard web docroot
* Web app should use the database tecc_webuser user account and provided root password
* Web app should read and write to the tecc_dba_test database table
* The web tier should scale between 2 and 4 VMs
* The test application, database schema, and database backup and restoral operation source code are in this repository.
* Specifically:
* Test Application
* Database Schema
* Backup
* Restoral

* 5. The IT manager has worked with the Information Security team and negotiated a security policy for the pilot. There must be limited secure access to any of the services in
the public cloud, only required TCP ports will be opened. Therefore, AWS security group configuration should:
* Allow SSH (TCP port 22) access from any IP address for all services
* Allow HTTP and HTTPS (TCP port 80 and 443) access from any IP address for the web service and Load Balancer
* Allow MySQL (TCP port 3306) database access from any IP address for the database service

Please create and test the blueprint. You may be able to adapt your blueprint from the course with changes to fit the project requirements, or you may want to start from 
scratch; either approach is acceptable.

Be sure to save your blueprint to your Udacity workspace before leaving a lab session!

![](https://raw.githubusercontent.com/ARBUCHELI/PROJECT-HYBRID-CLOUD-SAAS-THREE-TIER-WEB-APPLICATION/main/blueprint.jpg)

# Adaptation as a repository: Andrés R. Bucheli.


