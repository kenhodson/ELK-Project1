# ELK-Project1
The files in this repository were used to configure the network depicted below.

![Project 1 Diag](https://user-images.githubusercontent.com/87491789/150643084-51b6df57-b0e5-4055-8f2c-e24551388653.jpg)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbooks in this project may be used to install only certain pieces of it, such as Filebeat.

1.DVWA.yml
2.Elk-playbooke.yml 
3.Filebeat-playbook.yml
4.Metricbeat-playbook.yml

This document contains the following details:

- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

DESCRIPTION OF THE TOPOLOGY:

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing 
Load balancing ensures that the application will be highly effective, in addition to restricting traffic overload to the network.
Load balancers are created to protect networks against security threats such as Authenticating access for user. For example you can set it up to where the load balancer will require a username and password before granting access to your website to protect against unauthorized access. The Load balancer can also protect against DDoS. It does this by detecting and dropping distributed (DDoS) denial-of-service traffic before it gets to your website.
Jumpbox Provisioner
The jumpbox provisoner I used in my virtual netowrk makes it possible to SSH into the various networks such as from the REDNET to the ELKNET.

ELK server
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs.

Filebeat: Monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

Metricbeat: Helps you monitor your servers by collecting metrics from the system and services running on the server. Such as CPU, memory or data related to services running on the VM.


The configuration details of each machine may be found below.
| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            | 
| Web-1     | Webserver | 10.0.0.5   | Linux          |
| Web-2     | Webserver | 10.0.0.6   | Linux          |
| ELK-Server    | ELK   | 10.1.0.4   | Linux          |

ACCESS POLICIES:
The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
73.131.246.852

Machines within the network can only be accessed by SSH connection through port 22 from the Jumpbox machine.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 73.131.246.852    |

ELK CONFIGURATION:
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it leaves less room for human error and decreases man hours needed if we were to have to set it up manually.

The playbook implements the following tasks:
* Installs Docker container
* Installs python3
* Installs Docker Module
* Tells machine to use more memory RAM
* Download and loanches Docker ELK container
* Enables docker to start when booted


TARGET MACHINE AND BEATS:
This ELK server is configured to monitor the following machines:
Web-1 (10.0.0.5)
Web-2 (10.0.0.6)

We have installed the following Beats on these machines:
Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:

Filebeat is used to monitor the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing. During the process it would users logging in docker starting up and other OS events in Linux.

Metricbeat helps monitor your servers by collecting metrics from the system and services running on the server. Such as CPU, memory or data related to services running on the VM. This is in effect aour webservers 1 & 2 use Metricbeat to collect logs on the servers.

USING THE PLAYBOOK:
In order to use the playbook, you will need to have Ansible already configured. Assuming you have such this done: 

SSH into the control node and follow the steps below:
- Copy the ELK playbook file to the Jumpbox (Docker container host)
- Update the ELK file to include 
 
![image](https://user-images.githubusercontent.com/87491789/150894583-2ca26e5c-1a13-4d66-a6cb-ce73edc5838a.png)
 
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.
- You can navigate to the Public IP address (55.12.9.15) to make sure it is working.
