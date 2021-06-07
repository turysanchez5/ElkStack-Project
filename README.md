# ElkStack-Project

### 
Elk-Stack Project Summary

-Created a network security group (firewall rules)

-Created a virtual network

-Created a resource group

-Created virtual machines (JumpBox Provisioner, Web-1, Web-2)

-

DIAGRAM 

![](Project1.0.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

TODO: Enter the playbook file.
This document contains the following details:

Description of the Topologu
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable in addition to restricting traffic to the network.
  Load balancers are good to defend against denial-of-service (DDos) attacks.
  Jump box helps organizations to establish a clear funnel through which traffic must pass through to be able to traverse to other servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
  Filebeat is a logging agent installed on the machine generating log files or locations that you specify.
  Metricbeat collects metrics from your systems and services running on the server.

Name	        Function	     IP Address	  Operating System
Jump Box	    Gateway	        10.0.0.4	      Linux
Web-1	       Webserver-1      10.0.0.5        Linux
Web-2		     Webserver-2      10.0.0.7        Linux
		
Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
  23.102.152.252

Machines within the network can only be accessed by Jump Box virtual machine.

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it saves the admin time with their daily tasks.

The playbook implements the following tasks:

-Install docker

-Install python3-pip

-Install docker python module

-Set the max count to 262144

-Download and launch a docker elk container


Target Machines & Beats
This ELK server is configured to monitor the following machines:

Web-1 10.0.0.5
Web-2 10.0.0.7

We have installed the following Beats on these machines:

Filebeat

This Beat allows us to collect the following information from each machine:
  Monitors the log files or locations that you specify, which are used by us to see changes or messages the log files have      received.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

-Copy the ansible.cfg file to /etc/ansible

-Add the machine, IP address, and under ansible.cfg on hosts add ansible_python_interpreter=/usr/bin/python3

Ex.
  [webservers] 
  10.0.0.5 ansible_python_interpreter=/usr/bin/python3 
  10.0.0.7 ansible_python_interpreter=/usr/bin/python3
  
  [elk] 
  10.1.0.4 ansible_python_interpreter=/usr/bin/python3


Which file is the playbook? Where do you copy it?
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
_Which URL do you navigate to in order to check that the ELK server is running?
As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
