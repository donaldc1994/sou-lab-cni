# sou-lab-cni
DevOps – Vagrant, Ansible, Prometheus, Grafana e HaProxy

# Version v1.0
 - Creazione di un repository in GitHub denominato "sou-lab-cni".
 - Creazione di un progetto Vagrant multinodo (2 nodi: soufe1 e soube2) con comunicazone su interfacce network 
   locali (scegliere una subnet a piacere in 192.168.0.0/16).
 - Scegliere la distribuzione tra Centos, Almalinux, RockyLinux e Oracle Linux.

 # Notes per version v1.0
 - Reference links : 
    - https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html
    - https://mariadb.com/kb/en/creating-a-vagrantfile/ 
    - https://developer.hashicorp.com/vagrant/docs/vagrantfile 

# Version v1.1 
 - Creazione di un ruolo Ansible denominato sou_podman. Nei punti successivi sono espresse le azione che deve compiere l'automatismo.

# Notes  per version v1.1
 - Creo il ruolo: 
    - ansible-galaxy init sou_podman
 - Reference links : 
    - https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html 
    - https://spacelift.io/blog/ansible-roles 
    - https://www.devopsschool.com/tutorial/ansible/ansible-roles-explained-with-examples.html 