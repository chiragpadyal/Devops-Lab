# To install and configure software configuration management using Ansible

To install ansible run the following command:

```bash
sudo apt install ansible
```
After installing ansible check the version of ansible by running the following command:

```bash
ansible --version
```
the below commands will create a directory named playbooks in the ansible directory
```bash
cd /etc/ansible
sudo mkdir playbooks
cd playbooks
```


Let's write a yaml file to display content

```bash
gedit playbook1.yml
```

```yaml
- name: nginx install and start services
  hosts: all
  become: true

  tasks:
    - name: install nginx
      apt:
        name: nginx
        state: latest
    - name: start nginx
      service:
        name: nginx
        state: started
```
To run the playbook run the following command:

```bash
ansible-playbook playbook1.yml
```


This command will display the process id of nginx
 ```bash
ps-ef | grep nginx
``
