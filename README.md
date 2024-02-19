# Deployment-of-Ubuntu-Cluster-with-LAMP-Stack

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
  
  
  
