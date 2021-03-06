# project-1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: playbook5.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly Dynamic, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? They protect against a DDoS attack.
What is the advantage of a jump box? An advantage is that it is essentially a safe home for multiple different things to run off of.  

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the configeration and system files.
- _TODO: What does Filebeat watch for? The filebeat watches the log files and collects the log events.
- _TODO: What does Metricbeat record? It records metrics and stats from the OS from the server services.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function   | IP Address | Operating System |
|----------|----------  |------------|------------------|
| Jump Box | Gateway    | 10.0.0.1   | Linux            |
| web 1    | web access | 10.1.0.5   | Linux            |
| web 2    | web access | 10.1.0.6   | Linux            |
| elk stack| Kibana host| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 73.243.249.145

Machines within the network can only be accessed by SSH.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? I allowed the Jump Box and the IP is 10.0.0.8  

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.8             |
| Web 1    | No                  | 104.40.4.156         |
| Web 2    | No                  | 104.40.4.156         |
| ELK vm   | No                  | 23.96.11.24          |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? The main advantage is that it saves time.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- This installed the elk and let the two vnets talk to each other to keep things consistant. 
- This downloaded and installed docker inside the containers.
- This also helped us create a good server which was safe. 
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output] 



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: 10.0.0.5 10.0.0.6 10.0.0.4

We have installed the following Beats on these machines:
- _TODO: Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeat collects log files and collects the log events which we use to see traffic. Metric beat collects data from the OS and servers to see how things are running.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? My playbook5.yml
- _Which URL do you navigate to in order to check that the ELK server is running? http://23.96.11.24:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
