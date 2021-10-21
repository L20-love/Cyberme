# Cyberme
The files in this repository were used to configure the network depicted below.

TODO: Update the path with the name of your diagram

Images/elk-diagram.png
Images/finished-elk-diagram.png
Images/Finished-Cloud-Diagram
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook_ file may be used to install only certain pieces of it, such as Filebeat.

TODO: Enter the playbook file.
Filebeat.yml
This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Dmn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting access to the network.

TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
The load balancers protects the system from DDoS attacks by shifting attack traffic.
Advantage of a jumpbox The advantage of a jumpbox is to give access to the user from a single node that can be secured and monitored
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs___.

TODO: What does Filebeat watch for? Filebeat watches for log files and collects log events.

TODO: What does Metricbeat record? Metricbeat takes the metrics and statistics that collects and ships them to the output you specify.

The configuration details of each machine may be found below. Note: Use the Markdown Table Generator to add/remove values from the table.

Name	Function	IP Address	Operating System
Jump Box	Gateway	10.0.0.4	Linux
Elk-VM Server 10.1.0.4 Linux			
Web-1 Server 10.0.0.8 Linux			
Web-2 Server 10.0.0.7 Linux			
Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the jumpbox_____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

_TODO: Add whitelisted IP addresses_71.59.34.72
Machines within the network can only be accessed by __Jump-Box.

TODO: Which machine did you allow to access your ELK VM? What was its IP address?
jumpbox VM. IP address:10.0.0.4
A summary of the access policies in place can be found in the table below.

Name	Publicly Accessible	Allowed IP Addresses
Jump Box	/No	71.59.34.72
Web-VMs No 10.0.0.4		
Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

TODO: What is the main advantage of automating configuration with Ansible?
It allows you to deploy to multiple servers using a single playbook.
The playbook implements the following tasks:

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
Install Docker.io on the Elk machine
Install Python3-pip
Pip installs docker module
Use sysctl to increase system virtual memory
Download and launch a docker elk container with exposed ports
Enable docker service on boot.
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

TODO: Update the path with the name of your screenshot of docker ps output

Target Machines & Beats
This ELK server is configured to monitor the following machines:

TODO: List the IP addresses of the machines you are monitoring
Web-1: 10.0.0.8
Web-2: 10.0.0.7
We have installed the following Beats on these machines:

TODO: Specify which Beats you successfully installed
Filebeat
Metricbeat
These Beats allow us to collect the following information from each machine:

TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.
Filebeat collects log files from specific files on remote machines.
Metricbeat collects machine metrics. It is simply a measurement to tell analysts how healthy it is.
Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

Copy the filebeat-configuration.yml_file to _/etc/ansible/roles/files.

Update the filebeat-configuration.yml file to include...Elk IP in line 1106 and 1806

Run the playbook, and navigate to Elk-VM public IP to check that the installation worked as expected.

TODO: Answer the following questions to fill in the blanks:

Which file is the playbook? Where do you copy it?
Filebeat-playbook.yml. copied to: /etc/ansible/roles.
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
