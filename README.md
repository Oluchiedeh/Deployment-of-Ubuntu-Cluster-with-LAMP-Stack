# Deployment-of-Ubuntu-Cluster-with-LAMP-Stack

**Introduction**
As a devOps engineer, everthing you do is around software, website, application etc. So, there are different stack of technologies that make different solution possible, which are called WEB STACK. Web stack as also known as software stacks or technology stacks, which are used in web development to provide a cohesive set of technologies and tools for building web applications.
Exaamples of web stacks are listed below with it's different acronymns; 
- LAMP (Linux, Apache, MySQL, PHP or Python or Perl)
- LEMP (Linux, Nginx, MySQL, PHP or Python, or Perl)
- MERN (MongoDB, ExpressJS, ReactJS, NodeJS)
- MEAN (MongoDB, ExpressJS, AngularJS, NodeJS)

For this project, we will focus on LAMP web stack.

Further studies: 


**Prequisite:**

AWS account and a virtual machine with an Ubuntu server.

Spinning up a new EC2 instance (an instance of a virtual server) Click [HERE](https://medium.com/@oluchukwuedeh0/how-to-create-an-ec2-instance-on-aws-702116c4d4d5) for a step-by-step process to creating an EC2 instance in 3 mintues.

# Connecting to EC2 terminal/ Using the terminal on MAC/Linux.

The terminal is installed as a default, just open it.
- Navigate to where you downloaded youe key pair on your system, with this command:

 `cd download`.

- Change premissions for the private key file (.pem)

 `chmod 400 "project-server.pem"`.

- Connect to the instance by running.

  `ssh -i "project-server.pem" ec2-user@ec2-52-23-196-199.compute-1.amazonaws.com`.

  -
  
  
  
