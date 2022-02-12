# Project-1## Automated ELK Stack Deployment

```

```

```
The files in this repository were used to configure the network depicted below.
```

```
sysadmin@UbuntuDesktop:~/Downloads/README/Project-1$
```

```
**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  
```

```
sysadmin@UbuntuDesktop:~/Downloads/README/Project-1/diagrams/Project1.jpg
```

```
![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)
```

```

```

```
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the "YML" and/or "Config" file may be used to install only certain pieces of it, such as Filebeat.
```

```

```

```
  - _TODO: Enter the playbook file._
```

```
sysadmin@UbuntuDesktop:~/Downloads/README/Project-1/ansible/install-elk.yml
 
```

```
This document contains the following details:
```

```
- Description of the Topologu
```

```
- Access Policies
```

```
- ELK Configuration
```

```
  - Beats in Use
```

```
  - Machines Being Monitored
```

```
- How to Use the Ansible Build
```

```

```

```

```

```
### Description of the Topology
```

```

```

```
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
```

```

```

```
Load balancing ensures that the application will be highly "AVAILABLE", in addition to restricting "TRAFFIC" to the network.
```

```
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
```

```
"Availability, Web traffic flow, Web Security/reliability"
"Advantges of a JumpBox are Automation, segmentation, access control."
```

```
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the "DATA" and system "LOGS".
```

```
- _TODO: What does Filebeat watch for?_ "Filebeat watches for logs, locations collecting log events and pushing them to Elasticsearch or Logstash for further analysis." 
```

```
- _TODO: What does Metricbeat record?_ "Metricbeat, similar to Filebeat records log metrics and statistics and can be sent/forwarded to Elasticsearch and Logstash"
```

```

```

```
The configuration details of each machine may be found below.
```

```
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
```

```

```

```
| Name     | Function | IP Address | Operating System |
```

```
|----------|----------|------------|------------------|
```

```
| Jump Box | Gateway  |10.0.0.4/20.127.96.187  | Linux            |
```

```
 Web-1     | Web-Server   |10.0.0.5    |    Linux              |
```

```
| Web-2     |  Web-Server  | 10.0.0.6     |         Linux         |
```

```
| Web-3     |(Redundant web-server)| 10.0.0.7 |      Linux            |
```

```
| Elk VM   | ELK Server  |10.1.0.4/40.78.49.92|  Linux 
```

```
### Access Policies
```

```

```

```
The machines on the internal network are not exposed to the public Internet. 
```

```

```

```
Only the "ELK" machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
```

```
- _TODO: Add whitelisted IP addresses_: 66.44.18.66 (personal IP)
```

```
"Personal public IP allowed through TCP 5601"
```

```
Machines within the network can only be accessed by JUMPBOX.
```

```
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
```

```
"JumpBox IP: 10.0.0.4"
```

```
A summary of the access policies in place can be found in the table below.
```

```

```

```
| Name     | Publicly Accessible | Allowed IP Addresses |
```

```
|----------|---------------------|----------------------|
```

```
| Jump Box | NO              | Personal IP    |
```

```
| Web 1,2 | NO                    |  10.0.0.4         |
```

```
| ELK-VM   |    no              | Personal IP via 5601  |
```

```
Load Balancer (Red Team)| NO| Personal IP via http P.80 |
```

```
### Elk Configuration
```

```

```

```
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
```

```
- _TODO: What is the main advantage of automating configuration with Ansible?_
```

```
"It saves you time, energy, resources, while also reducing chance of human error. Once the first  configuration works you can continue to repeat using same script (playbook). If specific things need to be changed you can alter the playbook or create an alternative playbook, playing the playbook as opposed to writting out all the commands individually each time.
```

```
The playbook implements the following tasks:
```

```
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
```

```
- Specifies the machine and the user.
-Installs 3 programs/services: docker.io, pythonpip-3, docker
```

```
- Increases the system's memory.
```

```
-Opens 3 ports: 5601, 9200, 5044
```

```
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
```

```
Screenshot can be seen in sysadmin@UbuntuDesktop:~/Downloads/README/Project-1/diagrams$ 
```

```
**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  
```

```

```

```

```

```
![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
```

```
"sysadmin@UbuntuDesktop:~/Downloads/README/Project-1/diagrams/Docker_PS.png"
```

```
### Target Machines & Beats
```

```
This ELK server is configured to monitor the following machines:
```

```
- _TODO: List the IP addresses of the machines you are monitoring_
```

```
Web 1: 10.0.0.5
web 2: 10.0.0.6
```

```
We have installed the following Beats on these machines:"Elk-VM, Web-1, Web-2"
```

```
- _TODO: Specify which Beats you successfully installed_
```

```
Filebeat, Metricbeat
```

```
These Beats allow us to collect the following information from each machine:
```

```
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
```

```
Filebeat collects log events, Metricbeat collects metric and system statistics.
```

```
### Using the Playbook
```

```
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 
```

```

```

```
SSH into the control node and follow the steps below:
```

```
- Copy the "fileBeat-config.yml file to filebeat-playbook.yml. (same steps for Metricbeat. just change file to metric)
```

```
- Update the Filebeat file to include... https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.6.1-amd64.deb
-Update the Metricbeat file to include...
https://gist.githubusercontent.com/slape/58541585cc1886d2e26cd8be557ce04c/raw/0ce2c7e744c54513616966affb5e9d96f5e12f73/metricbeat 
```

```
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.
```

```

```

```
_TODO: Answer the following questions to fill in the blanks:_
```

```
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ "Configure/edit your hosts file (also uploaded in Ansible repository). Include the IP example:
10.0.0.6 anible_python_interpreter=/usr/bin/python3"
```

```
- _Which URL do you navigate to in order to check that the ELK server is running?
"http://40.78.49.92:5601/app/kibana. (the ELK publick IP with port 5601 (open))
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

Full log in and playbook:
sysadmin@UbuntuDesktop:~/.ssh$ sudo ssh -i RedteamSSH azdmin@20.115.106.249

azdmin@JumpBoxProvisioner:~$ sudo docker container list -a
azdmin@JumpBoxProvisioner:~$cd sudo docker start vigilant_wilson
azdmin@JumpBoxProvisioner:~$ sudo docker attach vigilant_wilson
root@73441e13c261:~# ansible-playbook /etc/ansible/pentest.yml 


azdmin@JumpBoxProvisioner:~$ sudo docker attach vigilant_wilson
root@73441e13c261:/etc/ansible# ansible-playbook install-elk.yml 
root@73441e13c261:/etc/ansible/roles# ansible-playbook filebeat-playbook.yml
root@73441e13c261:/etc/ansible/roles# ansible-playbook metricbeat-playbook.yml 
```