# Kubernetes


![images (1)](https://user-images.githubusercontent.com/71714243/111205849-b1b36700-85ed-11eb-936b-6c0cfec0b3e5.jpg)

The repository for creating Kubernetes Cluster using Ansible Roles. 


## The Roles
The folder named **K8s_Cluster_Roles** has three roles named **EC2_instance** , **K8_Master** , **K8_Slave** . The role launches two instances over aws cloud , configures one instance as _Master_ , other instance as _Slave_ respectively.

## The inventory
The folder named **/mydb** is used to setup the dynamic inventory which will automatically load the IPs of the instances. It contains two files namely ec2.py and ec2.ini. Follow the changes made in the file and make them executable using 
                                            **chmod +x filename**
                                            
## The configuration file
Ansible configuration file is located in **/etc/ansible/ansible.cfg** as a default location. We add the following parameters to execute the playbook remotely - connection , remote user , path of key to your AWS account. Since the instances launch will not have power to executethe tasks add privilege escalation to your config file. Since, we going to run roles add the role path and certain other details as well.

## The mainsetup file
The main setup file contains three hosts with their respective roles . The role which launches instance is run localy. The other two are run respectively on the name assigned to them while launching **tag_Name_nameofinstance** . In the end run this file to configure the entire structure using the command:
                                                                          **ansible-playbook filename**


![67fb22aa0142b62effc23870f80cf39d](https://user-images.githubusercontent.com/71714243/111205712-892b6d00-85ed-11eb-9c7b-3e97a1af880a.jpg)
