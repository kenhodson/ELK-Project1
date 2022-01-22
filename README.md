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

DESCRIPTION OF THE TOPOLOGY

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


