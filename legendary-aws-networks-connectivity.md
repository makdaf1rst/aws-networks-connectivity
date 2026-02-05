<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** saqibh49@gmail.com  
**Email:** saqibh49@gmail.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a separate space within the AWS bubble and it is useful because it provides a steructured space for people to store private data without it being accessible to just anyone on the internet.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a public and private subnets, route tables, NACLs, and security groups, then connect them with pulic and private servers and test the connection between my two servers and the connection between my public server and the internet.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how confusing it can get juggling between multiple subnets, NACLs , security groups and more if you don't keep yourself organized.

### This project took me...

This project took me about 40 minutes

---

## Connecting to an EC2 Instance

Connectivity is used to describe how well resources in my network talk to each other and to external networks.  

My first connectivity test was whether I could connect to my public server

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a way to connect dirrectly to my instance using SSH but without the need for key pairs since it's managed by AWS.

My first attempt at getting direct access to my public server resulted in an error, because the permissions in my public security group were set to allow all HTTP traffic but I was trying to access it via SSH, so I added the permission and it started working.

I fixed this error by aadding the permission to my public security group to allow all SSH traffic.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a way of checking if a server is connected to another server, kind of like saying hi and waiting for a repsonse. I used ping to test the connectivity between my public server and private server.

The ping command I ran was ping 10.0.0.141.9

The first ping returned was PING 10.0.141.9 (10.0.141.9) 56(84) bytes of data. This basically means that the ping was sent but without anymore lines coming back, that means the other server didn't respond.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by allowing the specific type of traffic I was sending the private server in my NACL and private security group settings.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a request to a server to send the raw HTML from the site on that server. 

I used curl to test the connectivity between my public server and the internet.

### Ping vs Curl

Ping and curl are different because ping just tests whether two servers are connected or not and the speed at which packages are sent and received. Curl, on the other hand, also retreives data from the other server, in this case the HTML associated with the server.

---

## Connectivity to the Internet

I ran the curl command curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3, which returned the full HTML code from the website in my curl command.

![Image](http://learn.nextwork.org/grateful_white_lucky_bat/uploads/aws-networks-connectivity_8ee57662)

---

---
