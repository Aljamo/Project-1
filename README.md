This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available _____, in addition to restricting access_____ to the network.
- _TODO: What aspect of security do load balancers protect? Availability and redundancy What is the advantage of a jump box?_limiting access to the network

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_It collects log files and sends entries to elastic search for further parsing.
- _TODO: What does Metricbeat record?_It collects system and service metrics like memory and cpu usage

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

|   Name     | Function             |  IP Address       | Operating System |
|-------------- |-----------------------|----------------------|--------------------------|
| Jump Box |Gateway             | 104.41.145.114 | Linux                      |
| Elk            | analyze logs      | 10.1.0.4             | Linux                      |
| Web 1       | Virtual Machine | 10.0.0.5             | Linux                      |
| Web 2       | VIrtual Machine | 10.0.0.6             | Linux                      |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the host machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_104.34.226.252

Machines within the network can only be accessed by _jump box____.
- _TODO: Which machine did you allow to access your ELK VM? _jump box What was its IP address?_10.1.0.4 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes            | 104.34.226.252 |
| Web1        | No             |  10.0.0.5            |
| Web2        |  No            |  10.0.0.6            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
It saves time which allows for more productivity
It eliminates repetitive tasks
Fewer mistakes & errors
Improve collaboration and job satisfaction
Overcome complexity
More resources for innovation
Increase accountability and compliance

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ???sudo apt install docker.io
- ...which was used to install the ELK container
-...configured to take logs from web 1 and web 2
-...


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ Web1 10.0.0.5, Web2 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_Filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._ Filebeat monitors the log files and log events.  I expect to see different information about the logs.

Metricbeat collects metrics and the services as well as the statistics.  I expect to see important info about the services that are running

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat. deb_____ file to _____.
- Update the _playbook ____ file to include...filebeat.deb
- Run the playbook, and navigate to _kibana___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? 
13.77.163.173:5601



_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

