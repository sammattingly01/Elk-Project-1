# Elk-Project-1
Repository for my Elk Project 1, showing diagrams and scripts from my Elk server.
Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

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
Load balancing ensures that the application will be highly functional and available, in addition to restricting traffic to the network.
What aspect of security do load balancers protect? What is the advantage of a jump box?
Load balancers add resiliancy by rerouting live traffic from one server to another if a server falls prey to a DDoS attack or otherwise becomes unavailable.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.
What does Filebeat watch for? Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to elastic research or logstash for indexing.
What does Metricbeat record? Mericbeat takes the metrics and statistics that is collects and ships them to the output that you specify, such as elasticsearch or logstash.
The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.



Name
Function
IP Address
Operating System




Jump Box
Gateway
20.211.178.90
Linux


web-1
ubuntu
20.213.148.90
Linux


web-2
ubuntu
20.213.148.90
Linux


dvwa-vm2
ubuntu
20.213.148.90
Linux


Elk
ubuntu
20.89.141.17
Linux




Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Workstation My public IP through TCP 5601.
Machines within the network can only be accessed by Workstation and Jump-box provisioner through SSH Jump-Box.
Which machine did you allow to access your ELK VM? What was its IP address?
Jump-box Provisioner IP: 10.0.0.4 via port 22
Workstation my public IP via port TCP 5601
A summary of the access policies in place can be found in the table below.



Name
Publicly Accessible
Allowed IP Addresses




Jump Box
Yes
10.0.0.4


web-1
No
10.0.0.5


web-2
No
10.0.0.6


dvwa-vm2
no
10.0.0.7


elk
no
10.1.0.5




Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible?
There are multiple advantages. Ansible lets you quickly and easily deploy multiple applications through a YAML playbook. You don't need to write custom code to autonate your systems. Ansible will also figure out how to get your systems to the state you want them to be in.
The playbook implements the following tasks:
In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Target Machines & Beats
This ELK server is configured to monitor the following machines:
List the IP addresses of the machines you are monitoring:
web-1: 10.0.0.5
web-2: 10.0.0.6
DVWA-rw2: 10.0.0.7
We have installed the following Beats on these machines:
Filebeat and Metricbeat
These Beats allow us to collect the following information from each machine:
Filebeat will be used to collect log files from very specific files such as apache, microsoft azure tools and web servers, MySQl databases. Metricbeat will be used to monitor VM stats, per CPU core stats, per filesystem stats, memory stats and network stats.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the yml file to ansible folder.
Update the config file to include remote users and ports.
Run the playbook, and navigate to kibana to check that the installation worked as expected.

TODO: Answer the following questions to fill in the blanks:

_Which file is the playbook? Where do you copy it? /etc/ansible/hosts file
_Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? I have specific two seperate groups in the /etc/ansible/hosts file. One of the group will be webservers which has the IP's of the 3 VM's that I will install filebeat to. The other group is named ELKserver which will have the IP's of the VM I will install ELK to.
_Which URL do you navigate to in order to check that the ELK server is running?

As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
