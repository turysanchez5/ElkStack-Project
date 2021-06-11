## Elk-Stack Project 1

The following diagram shows a visual picture of our Elk Stack project.

![](ElkProject.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the roles file may be used to install only certain pieces of it, such as Filebeat.

Playbook file: under the containers root access /etc/ansible/elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting traffic to the network.
- _Load balancing ensures that the application will be highly reliable in addition to restricting traffic to the network.
  Load balancers are good to defend against denial-of-service (DDos) attacks.
  Jump box helps organizations to establish a clear funnel through which traffic must pass through to be able to traverse to other servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _  Filebeat is a logging agent installed on the machine generating log files or locations that you specify.
- _  Metricbeat collects metrics from your systems and services running on the server.

The configuration details of each machine may be found below.


| Name      | Function | IP Address | Operating System |
|-----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web-1     | WebServer| 10.0.0.5   | Linux            |
| Web-2     | WebServer| 10.0.0.7   | Linux            |
| Elk-Server| Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _23.102.152.252

Machines within the network can only be accessed by Jump Box virtual machine.
- _Which machine did you allow to access your ELK VM?
- _ Public IP from home.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | Home IP Address      |
| Web-1    | No                  | 10.0.0.4             |
| Web-2    | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it saves the admin time with their daily tasks.

The following are the steps of the ELK installation.

- I installed docker.io as well as python-pip and docker.
- Ran the command systctl -w vm.max_map_count=262144
- Ended with launching the docker container elk.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _Web-1 10.0.0.5
- _Web-2 10.0.0.7

We have installed the following Beat on these machines:
- _Filebeat

These Beats allow us to collect the following information from each machine:
- _Filebeat allows us to monitor the log files/locations that you are looking for, which allows us to see any messages or changes that have happened.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

- _SSH into the control node and do the following:
- _ Copy the filebeat.yml to /etc/filebeat directory.
- _ Update the filebeat-playbook.yml file to include where to install the ELK server with the dpkg command and install filebeat in the roles directory
- _ Run the playbook


