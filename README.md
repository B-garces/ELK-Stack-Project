# ELK-Stack-Project
Configured an ELK stack server in order to set up a cloud monitoring system. Demonstrates cloud, network security, logging and monitoring.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._ 
	install-elk.yml
         filebeat-playbook.yml


This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _reliable____, in addition to restricting __access___ to the network.
- _TODO: What aspect of security do load balancers protect? It protects overloading on servers preventing targeted ddos attacks. What is the advantage of a jump box?_ establishes a clear tunnel where traffic can run through before connceting to VMs allowing more control on security

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __VMs___ and system _Logs____.
- _TODO: What does Filebeat watch for?_ log data
- _TODO: What does Metricbeat record?_ collects metric from the OS

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Elk      | Processes data from multiple data sources | 10.1.0.4 |     |
| Web-1    | Web server| 10.0.0.7  |                  |
| Web-2    | Web server| 10.0.0.9  |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __host___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_ 173.56.15.215

Machines within the network can only be accessed by _jumpbox____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ Jumpbox & web1 & web2 : 10.0.0.7, 10.0.0.9,10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ Way to automate tasks to run rather then doing it manually all the time.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- First the memory was established to how mcuh ram the elk container will use when running. Then the apt packages are ran to get the docker engine (docker.io) and the python package to install the python software to read the data.
- Then intalled docker which is the pthon client for docker to run. Next step would be to actually donwload the elk docker container. then the last part would be allowing the port mappings for port 5601,9200 and 5044. 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output] (Images/docker_ps_output.png) https://gyazo.com/e5ed94d640f2ea168169800797bf769a

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ 10.0.0.7 10.0.0.9 

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ Filebeats and metricbeats

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Metricbeat collects metrics from the OS taking in statsistics and collects them to send out to certains outputs. Firebats collects and monitors log data for later use of indexing.


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? By updating to the current local host then changing it to be accessed in the ansible config file. How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? http://localhost:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
