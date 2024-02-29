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

![](update.png)

**Run Apache2 package installation.**

`sudo apt install apache2`

![](installation.png)

**To verify that apache2 is running as a Service in our OS, use the following command.**

`sudo systemctl status apache2`

![](activeaapache.png)


Before we can receive any traffic from our Web Server, we need to open TCP port 80 which is the default port that web browsers use to access web pages on the Internet

As we know, we have TCP port 22 open by default on our EC2 machine to access it via SSH, so we need to add a rule to the EC2 configuration
to open an inbound connection through port 80: Open inbound port 80 - http - Anywhere from IPV4 on your security rule.

Now it is time for us to test how our Apache HTTP server can respond to requests from the Internet.

Open a web browser of your choice and try to access the following URL

http://(Public-IP-Address)

![](apache.png)

You can get your Public IP Address on the AWS EC2 console.


# STEP 2 - INSTALLING MYSQL.

We have a web server up and running, you need to install a Database Management System (DBMS) to be able to store and manage data for your website in a relational database (A relational database is a type of database that organizes data into tables, where each table represents a collection of related data entries). MySQL is a popular relational database management system used within PHP environments. Other relational databases are; PostgreSQL, Oracle Database, Microsoft SQL Server, and SQLite.

**To acquire and install this software we will be using apt.**

`sudo apt install mysql-server`

**Once installation is completed, Log in.**

`sudo mysql`

This will connect to the MySQL server as the administrative database user root. You should see output like this:

**Secure the script.**

It's recommended that you run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lock down access to your database system. Before running the script you will set a password for the root user, using mysql_native_password as the default authentication method. We're defining this user's password as PassWord.1.

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWORD.1';`

**Exit the MySQL shell with:**

`exit`

**Start the interactive script by running:**

`sudo mysql_secure_installation`

This will ask if you want to configure the VALIDATE PASSWORD PLUGIN.
**Press 'N'**

For the rest of the questions, press Y and hit the ENTER key at each prompt. This will prompt you to change the root password,
remove some anonymous users and the test database, disable remote root logins, and load these new rules so that MySQL immediately respects the changes you have made.

**When you're finished, test if you're able to log in to the MySQL console by typing and exit:**

`sudo mysql -p`

`exit`
