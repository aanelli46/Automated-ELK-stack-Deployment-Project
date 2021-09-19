# Automated-ELK-stack-Deployment-Project
Automated ELK stack Deployment 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/aanelli46/Automated-ELK-stack-Deployment-Project/blob/main/Diagrams/Azure%20Network%20Diagram.drawio.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - elk-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.6   | Linux            |
| azdmin   | server   | 10.0.0.4   | Linux            |
| Web22    | server   | 10.0.0.8   | Linux            |
| elkstack | server   | 10.2.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
     

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1 10.0.0.2    |
| azdmin   | no                  |                      |
| web22    | no                  |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible is simple, reliable, and easy to install.  If you want to install an updated version of a specific type of software on all the machines in your enterprise, all you have to do is write out all the IP addresses of the nodes (also called remote hosts) and write an Ansible playbook to install it on all the nodes, then run the playbook from your control machine.

The playbook implements the following tasks:

Install: docker.io
Install: python-pip
Install: docker
Command: sysctl -w vm.max_map_count=262144
Launch docker container: elk
 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 
10.0.0.4
10.0.0.8

We have installed the following Beats on these machines:
- Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat will collect any changes made.
Metric beat will collect the metrics and statistics

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

- Which file is the playbook? 
     /etc/ansible/roles/filebeat-playbook.yml
- Which file do you update to make Ansible run the playbook on a specific machine? hosts

[web_servers] will have filebeat

How do I specify which machine to install the ELK server on 
versus which to install Filebeat on?
[elk] above 10.2.0.4

- _Which URL do you navigate to in order to check that the ELK server is running?
[web_servers] will have filebeat
