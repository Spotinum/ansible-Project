### How to run ansible with vagrant
* Go to the directory where VagrantFile is located
* Run in terminal in order to start all the vms
```bash
 vagrant up
```

* Type in order to add the ssh config.
```bash
ssh-config >> ~/.ssh/config
```
* Once all the vms are up and running, go to the directory where ansible.cgf is located
* Run in terminal for postgres

```bash
ansible-playbook -l dbserver-vm playbooks/postgres.yaml
```


* Run in terminal for spring
```bash
ansible-playbook -l appserver-vm playbooks/spring.yaml
```

* Run in terminal for vue
```bash
ansible-playbook -l frontend-vm playbooks/vuejs.yaml
```

Once everything is up and running head to your broswer and type in the ip: 192.168.56.103


### How to run docker with vagrant and ansible
* Go to the directory where VagrantFile is located
* Run in terminal in order to start all the vms
```bash
 vagrant up docker
```

* Type in order to add the ssh config.
```bash
ssh-config >> ~/.ssh/config
```
* Once the vm are up and running, go to the directory where ansible.cgf is located

* Run in terminal for spring
```bash
ansible-playbook -l docker-vm playbooks/spring-vue-docker.yml
```

Docker will be installed to that vm if it is not already installed. Once the playbook is finished type in your broswer this ip: 192.168.56.104

### How to run K8s with ansible on virtual vm
* Go to the directory where ansible.cfg is located
* Make sure you have the k8s-vm up and running in host.yaml
* Run in terminal to start the playbook
```bash
ansible-playbook -l k8s-vm playbooks/k8s.yaml
```

The application should start running after a while, type in your broswer the dns name you have set in vue-ingress.yaml 