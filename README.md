# Deployment-of-Ubuntu-Cluster-with-LAMP-Stack

**Introduction**
As a DevOps engineer, everything you do is around software, websites, applications, etc. So, different stacks of technologies make different solutions possible, called WEB STACK. Web stacks also known as software stacks or technology stacks, are used in web development to provide a cohesive set of technologies and tools for building web applications.

Examples of web stacks are listed below with their different acronyms; 
- LAMP (Linux, Apache, MySQL, PHP or Python or Perl)
- LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
- MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
- MEAN (MongoDB, ExpressJS, AngularJS, NodeJS)
For this project, we will focus on the LAMP web stack.

**Prerequisite:**

AWS account and a virtual machine with an Ubuntu server.

Spinning up a new EC2 instance (an instance of a virtual server) Click [HERE](https://medium.com/@oluchukwuedeh0/how-to-create-an-ec2-instance-on-aws-702116c4d4d5) for a step-by-step process to creating an EC2 instance in 3 mintues.

# Connecting to EC2 terminal/ Using the terminal on MAC/Linux.

The terminal is installed as a default, just open it.
- Navigate to where you downloaded your key pair on your system, with this command:

 `cd download`.

- Change premissions for the private key file (.pem)

 `chmod 400 "project-server.pem"`.

- Connect to the instance by running.

  `ssh -i "project-server.pem" ec2-user@ec2-52-23-196-199.compute-1.amazonaws.com`.
  
  

  ![](ssh-page.png)


**Next, configure the created EC2 Instance machine to serve a web server.**

  
# Step 1: INSTALLING APACHE AND UPDATING THE FIREWALL.

Apache, also known as Apache HTTP Server, is a widely used open-source web server software. It is maintained and developed by the Apache Software Foundation, a community of developers that collaborates on various open-source projects.

Apache serves web pages and other content over the internet. Apache processes incoming requests from web clients (such as web browsers), and delivers the requested content, which includes HTML pages, images, videos, or other files.


Install Apache using Ubuntu's package manager 'apt':
  
**Update a list of packages in the package manager.**

`sudo apt update`

**Run Apache2 package installation.**

`sudo apt install apache2`


**To verify that apache2 is running as a Service in our OS, use the following command.**

`sudo systemctl status apache2`
