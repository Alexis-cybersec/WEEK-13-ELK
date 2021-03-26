# WEEK-13-ELK
Week 13 HW
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, se>
  - _TODO: Enter the playbook file._ filebeat-playbook.wml (filebeat and metricbeat are in this file)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly Dynamic, in addition to restricting Access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
-The Load Balancers protecvt the servers from any unauthorized traffic from the web. if a DDOS attack happens it helps prevent the damage it can do.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Configuration and system Files.
- _TODO: What does Filebeat watch for?_
        -it looks for log files, collects and logs any events and sends them to kibana for their records.
- _TODO: What does Metricbeat record?_
        -it collects metric info from the OS and services.
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function   | IP Address | Operating System |
|------------|------------|------------|------------------|
| Jump Box   | Gateway    | 10.0.0.1   | Linux            |
| ELK VM     | Web Server | 10.2.0.0   | Linux            |
| ELK_WEB-1  |            | 10.2.0.4   |                  |
### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_
        -107.204.176.39
Machines within the network can only be accessed by JumpBox Provisioner.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
        -jumpbox porvisioner has access with the ip being 13.64.198.171
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1             |
| WEB-1    | No                  | 13.64.198.171        |
| WEB-2    | No                  | 13.64.198.171        |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
        -it has many advantages and you can use the configuration file to set specific groups to routers and machines
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io in the system
- Install python-3 pip
- Install python package docker
- Download Elk image and open the ports for kibana to use

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
        - JumpBox 13.64.198.171
        - WEB-1 10.2.0.4
        - WEB-2 10.2.0.6We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
        - filebeat & metricbeat
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we >        - filebeat monitors any changes made within the system and metricbeat monitors the metrics such as RAM, HDD Space, Tasks, etc,
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the filebeat-playbook.yml file to etc/ansible/roles.
- Update the /etc/ansible/hosts file to include...
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
        - file is called filebeat-playbook.yml and its located in /etc/ansible/rules
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Fileb>        update ansible file and the correct IP in the file for the ELK server
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

